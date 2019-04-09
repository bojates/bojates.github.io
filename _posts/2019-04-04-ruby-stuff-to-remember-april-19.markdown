---
title: Ruby stuff to remember April '19
layout: post
---

 - Methods should only do one thing; they should be under 15 lines
 - Method should either return a usable value or perform side effects; not both
 - Method name should reflect whether side effects occur or not; should reflect functionality
     + Ex. method called `total` will return a total; don’t need to name it `return_total`
 - Methods should a black box; should be able to use in irb with input and get output
 - When you have multiple methods, they should be at the same level of abstraction
 - Method name should say what method does but not how; implementation is up to code
 - If a method mutates a parameter passed in, should reflect that in the name
 - If method is mutating, should return a value
 - If a method displays something, make sure to prefix it with `print_`, `say_`, or `display_`
    - Ex. method `welcome` may print “welcome” or return welcome; use `print_welcome`
 - A program should only have one exit point
 - Don’t mutate the caller during iteration; if iterating over a string, don’t delete characters
 - You shouldn’t mutate the collection; however collection elements can be mutated
 - Don’t choose block variables (within `||`) with the same name as other variables; otherwise, these other variables become inaccessible due to variable shadowing
 - If you have unused parameters, use _ to signify that you don’t care about it

## Stuff I think I do ok already
 - Always use two spaces for indents
 - Method, variables, or file name should always be snake_case; classes are in CamelCase

(based on [this cheatsheet](https://mylsjourney.com/ruby-quick-reference/))
