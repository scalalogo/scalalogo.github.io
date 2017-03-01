---
layout: default
---

[Back to table of contents](/en)  
[Previous: Introduction](/en/1_introduction)  
[Next: Functions](/en/3_functions)  

## Variables

In the example in the previous chapter, we always moved the turtle 30 steps. Imagine that now you want to make the same drawing but twice as big. You would have to change that 30 to 60 in each place separately. Instead, you could create a variable: `val size = 30` and then use it in all places this way: `move(size)`. This way, changing the size of the drawing would only require changing only one line: writing `val size = 60` instead of `val size = 30`.

TODO iframe

Another way of creating a variable is: `var size = 30`, which differs from the previous one in the first word - it's `var` instead of `val`. If a variable is declared as a var, it means that it's value can change during the execution of a program:

```scala
var size = 20
(...)
size = 30
```

This would not be possible if a variable was a val.

### Example

Let's create a beginning of a square spiral. We'll start with a segment of length 10 and 90 degrees rotation and repeat that a few times, extending the length of each next segment by 10.

TODO iframe

## Conditionals

Sometimes we might want to perform some action depending on some condition. This is where conditional statements come in handy. In our case the simplest conditions can be based on some properties of numerical variables such as for example:

* `n > 5` - true if variable n is greater than 5
* `n >= 5` - true if n is greater than or equals 5
* `n < 5` - true if n is smaller than 5
* `n <= 5` - true if n is smaller than or equals 5
* `n == 5` - true if n equals 5
* `n != 5` - true if n does not equal 5
* `n % 2 == 0` - true if n is even
* `n % 2 != 0` - true if n is odd

The simplest example would be if we wanted to run some code only if some condition was true.

```scala
if (condition) {
  //the code here is executed only if the condition is true
}
```

We might also want to execute some other code if the condition is false. Then the code looks like this:

```scala
if (condition) {
  //the code here is executed only if the condition is true
} else {
  //the code here is executed only if the condition is false
}
```

TODO examples

It is also possible to depend a value assinged to a variable on some condition in a very concise way like this: `val s = if (n >= 0) n else -n`. This snippet assigns the value of n to s if n is non-negative and the opposite number (-n) if n is negative - either way, the value of s won't be negative.

We will use it in the example below to create a triangle - a green one if size is greater than 30, a red one otherwise. Try changing the value of size and see the result.

TODO iframe

## Loops

Very often we want to execute the same (or similar) piece of code consecutively. The simplest way to achieve this (which is not a part of Scala Standard Library nor is it a loop) is:

```scala
repeat(10) {
  //put code here
}
```

Any code put in braces will be repeated 10 times. Of course, number 10 was chosen arbitrarily. You can also use an integer variable (or statement) instead.

```scala
val N = 5
repeat(N) {
  //code A
}
repeat(N + 2) {
  //code B
}
```

In the example above "code A" will be repeated 5 times, and "code B" will be repeated 7 times.

The `repeat` construct allows only simple repetition. For example, we wouldn't be able to use it in our example for drawing a square spiral. However, we could use a `for` loop.

```scala
for(i <- 1 to 10) {
  move(i * 10)
  rotate(90)
}
```

In this example the code inside braces will be executed 10 times. Why? Because of `i <- 1 to 10` - this means that during each subsequent execution the variable `i` will have different value: starting with 1, then 2, 3, and so on, and finally 10, which together makes ten times! As a result we will draw ten sides of a spiral - with lengths 10, 20, 30, ..., 100 respectively.

There are various other forms of `for` loops in Scala, however we won't go into details about them.

Another similar construct is a `while` loop.

```scala
while(condition) {
  //put code here
}
//some other code
```

The `condition` here can be any statement with a boolean value (see the "Conditionals" section above). The execution goes as follows:

1. the condition is evaluated
2. if it's false, all the code in braces is omitted and the execution moves to "some other code"
3. if it's true, the code in braces is executed and then **we go back to point 1**

In the example below you can see how the `while` loop was used for creating the quadratic spiral until the length of the side was larger than 200.

TODO iframe

<iframe height="600" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/8"></iframe>

[Back to table of contents](/en)  
[Previous: Introduction](/en/1_introduction)  
[Next: Functions](/en/3_functions)