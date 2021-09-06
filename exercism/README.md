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

