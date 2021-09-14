# Sorbet Syntax

## Table of Contents

* [Useful Resources](#useful-resources)
* [Examples](#examples)
  * [Basics](#basics)
  * [Simplest method signature](#simplest-method-signature)
  * [Simple method signature](#simple-method-signature)

## Useful Resources
  * [Sorbet Quick Reference](https://sorbet.org/docs/quickref)
  * [Sorbet Playground](https://sorbet.run)

### Basics

```ruby
# typed: true
require 'sorbet-runtime'
```

### Simplest Method Signature

```ruby
extend T::Sig

sig { void }
def some_function()
  puts 42
end
```

### Common Method Signatures

### 
```ruby
extend T::Sig

sig { params(x: Integer).void }
def some_function(x)
  puts x
end

some_function(42) #=> 42
some_function("42") #=> Expected Integer but found String("s") for argument x
```
