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

