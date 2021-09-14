# Sorbet Syntax

## Table of Contents

* [Examples](#examples)
* [Useful Resources](#resources)

## Useful References
  * [Sorbet Quick Reference](https://sorbet.org/docs/quickref)
  * [Sorbet Playground](https://sorbet.run)

## Examples

```ruby
# typed: true
require 'sorbet-runtime'
```

```ruby
extend T::Sig

sig { void }
def some_function()
  puts 42
end
```
