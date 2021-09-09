# Exercism, Ruby Track

## Table of Contents

* [Notes](#notes)

## Notes

> ... everything in Ruby is an object. Numbers, strings, arrays...

> Variables are always written in **snake case**.

Dynamically typed:

```ruby
some_variable = 42
some_variable = "Nyanpasu"
some_variable = SomeNPC.new
```

Ruby supports implicit return:

```ruby
def square(num)
  num * num
end
```

Keyword arguments:

```ruby
def multiply(num1:, num2:)
  return num1 * num2
end

calc.multiply(num1: 6, num_2: 7) # 42
```

Class constructor and instance variables:

```ruby
class SomeNPC
  def initialize
    @level = 42
  end
end
```

`nil`

Boolean logic:

* `&&` or `and`
* `||` or `or`
* `!` or `not`

> Single quotes do not allow interpolation, whereas double quotes do. Interpolation is where one string is included in another using the #{} syntax.

Interpolated string literal `%{... }`.

Non-interpolated string literal `%q{... }`.

String slices:

```ruby
some_string = "--Nyanpasu"

some_string[2]            #=> "N"
some_string.index('N')    #=> 2
some_string[2, 4]         #=> "Nyan"
some_string.slice(2, 4)   #=> "pasu"
```

Some common `String` methods:

* `capitalize`
* `downcase`
* `strip`
* `split`
* `center`
* `gsub` — global substitution(?), can take a regex matching pattern.
* `rjust`
* `ljust`

Some common `Number` methods:

* `Integer#to_f`
* `Float#ceil`
* `Float#floor`6 * 22
* `Float#round`
* `Float#to_i`

Throwing exceptions with `raise`:

```ruby
begin  
   puts 'Before the raise.'  
   raise 'ARGH!'  
   puts 'This one will never get printed.'  
rescue  
   puts 'Recovering...'  
end

puts 'Nyanpasu!'

#=> "Before the raise."
#=> "Recovering..."
#=> "Nyanpasu!"
```

> Module is Classes parent in the object hierarchy.

Module syntax:

```ruby
module Statistics
  def self.average(nums)
    # ...
  end
end

Statistics.average([ 1, 2, 3 ]);
```

`until` loop:

```ruby
i = 0

until i == 42
  i += 1
end
```

Arrays are zero-indexed in Ruby.

Negative index works on arrays in Ruby.

Common `Array` methods:

* `Array.size`
* `Array.sum`
* `Array.reverse`
* `Array.flatten`
* `Array.sort`

Enumeration of an array:

```ruby
words = [ "4", "2", "42" ]

words.each do |word|
  puts word
end
```

Some `Array` methods that take a *block*:

* `Array.sum` 
* `Array.count`
* `Array.any?`
* `Array.none?`
* `Array.select`
* `Array.all?`
* `Array.map`
* `Array.find`


Blocks are kind of like anonymous functions.

```ruby
nums = [ 1, 2, 3, 4, 42 ]

nums.count  { |num| num == 42 } #=> 1
```

The enumeration of `Hash`es has the same syntax as the enumeration of `Array`s:

```ruby
pet_names.each { |key, value| ... }
```

`OpenStruct` is like object in JavaScript:

```ruby
npc = OpenStruct.new({ name: "Nadeshiko", level: 42 })

npc.name #=> "Nadeshiko"
npc.level #=> 42
```

With `OpenStruct`, the following shorthand is available:

```ruby
npcs.sum { |npc| npc.level }
npcs.sum(&:level)
```

Using Ruby's Standard Library:

```ruby
require 'ostruct'

npc = OpenStruct.new({ name: "Nadeshiko", level: 42 })
```

Handling exceptions:

```ruby
begin
  # Code that raises and exception.
rescue => e
  # Logic that runs when an exception is raised.

  puts "Exception class: #{ e.class.name }"
  puts "Exception class: #{ e.message }"
end
```

Custom exceptions:

```ruby
class SomeError < StandardError
end

raise SomeError.new("Uwah!")
```

Block commenting:

```ruby
=begin
  All the things you want to say about the world.
=end
```

Unit testing:

```ruby
# some_module_test.rb

require 'minitest/autorun'
require_relative 'some_module' # some_module.rb

class SomeModuleTest < Minitest::Test
  def test_one
    assert_equal true, SomeModuleTest.some_method
  end
end
```

Sorting an `Array` on multiple values:

```ruby
arr = [
  { "a" => 4, "b" => 2 },
  { "a" => 2, "b" => 0 },
  { "a" => 1, "b" => 3 },
  { "a" => 4, "b" => 0 },
  { "a" => 0, "b" => 0 }
]

arr.sort_by { |h| [ h["a"], h["b"] ] }

=begin
  [
    { "a" => 0, "b" => 0 }, 
    { "a" => 1, "b" => 3 }, 
    { "a" => 2, "b" => 0 }, 
    { "a" => 4, "b" => 0 }, 
    { "a" => 4, "b" => 2 }
  ]
=end
```

Sorting a `Hash` on multiple values:

```ruby
h = {
  "m" => { "a" => 4, "b" => 2 },
  "n" => { "a" => 2, "b" => 0 },
  "o" => { "a" => 1, "b" => 3 },
  "p" => { "a" => 4, "b" => 0 },
  "q" => { "a" => 0, "b" => 0 }
}

h.sort_by { |_, v| [ v["a"], v["b"] ] }.to_h

=begin
  {
    "q" => { "a" => 0, "b" => 0 }, 
    "o" => { "a" => 1, "b" => 3 }, 
    "n" => { "a" => 2, "b" => 0 }, 
    "p" => { "a" => 4, "b" => 0 }, 
    "m" => { "a" => 4, "b" => 2 }
  }
=end
```

String formatting, rounding to 2 d.p. as an example:

```ruby
'%.4f' % 2.99792458

#=> "2.9979"
```

Collecting arguments with the `*` operator:

```ruby
def some_function(*args)
  return args == [ 1, 2, 3 ]
end

some_function(1, 2, 3)

#=> true
```

Use `**` for named arguments.

Calling a block inside a method with `yield`:

```ruby
def some_method()
  yield 42
end

some_method { |x| puts x }

#=> 42
```

A slightly more complex use case with refinement(?):

```ruby
class Array
  def inefficient_map
    return self.map { |x| yield x }
  end
end

[ 1, 2, 3 ].inefficient_map { |x| x * x }

#=> [ 1, 4, 9 ] 
```

