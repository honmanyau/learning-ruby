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

