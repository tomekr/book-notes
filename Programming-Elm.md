## Chapter 1: Get Started with Elm

> You use whitespace rather than commas to delimit multiple parameters.

```elm
> sayHello greeting name = greeting ++ ", " ++ name ++ "."<function> : String -> String -> String
```

> Calling a function with multiple arguments requires whitespace as well.

```
> sayHello "Hi" "Elm""Hi, Elm." : String
```

A higher-order function is basically a function that accepts another function as an argument or returns a function.

Functions are **first-class** citizens in Elm. They are values just like strings, numbers, and booleans.

```
> person "Jeremy" (\other -> sayHello "Hi" other) "Tucker""Hi, Tucker. My name is Jeremy." : String
```

You call it with "Jeremy" and "Tucker" again, but between those arguments you use an anonymous function. An **anonymous function** is like a regular function but has no name. Anonymous functions are great for creating functions on the fly.

Elm functions are **curried**, which is a fancy way of saying they take one argument at a time.

Filling in one argument at a time is known as **partial application**. Calling a function with only some of its arguments is _partially applying it_.

Currying and partial application are incredibly useful tools in Elm and functional programming. Sometimes developers confuse the two concepts, so to keep them straight you can remember this phrase:

**Create Curried functions, partially Apply Arguments.**

Every Elm file is a **module**. Modules let you organize code into logical units. Every module contains one or more constants and functions that it can expose to other modules. For 3exampke, you could build a Math module that exposes functions for addition and subtraction.

Left off at "Build a Static App"