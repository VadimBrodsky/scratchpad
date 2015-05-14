---
title: "Object Types: Booleans" 
layout: post
category: ruby
date: 2015-03-04 22:44:00 
---

- Boolean: True / False for comparisons.

|  Operator                        |  Syntax |
| :------------------------------- | :------ |
| Equal                            | `==`    |
| Less than                        | `<`     |
| Greater than                     | `>`     |
| Less than or equal to            | `<=`    |
| Greater than or equal to         | `>=`    |
| Not                              | `!`     |
| Not Equal                        | `!=`    |
| And                              | `&&`    |
| Or                               | <code>&#124;&#124;</code>    |
| Comparison* (spaceship operator) | `<=>`   |

Comparison is not a boolean operator.

```ruby
true.class              #=> TrueClass
false.class             #=> FalseClass
1 > 2                   #=> false
x.nil?                  #=> false
2.between?(1,3)         #=> true
[1,3,4].empty?          #=> false
[1,2,3].include?(3)     #=> true
hash.has_key?('a')      #=> false
hash.has_value?('zz')   #=> false
```