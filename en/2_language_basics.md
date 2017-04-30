---
layout: default
---

[Back to home page](/en)

[Previous: Introduction](/en/1_introduction)  
[Next: Functions](/en/3_functions)

## Variables

In the example in the previous chapter, we always moved the turtle 60 steps. Imagine that now you want to make the same drawing but twice as big. You would have to change that 60 to 120 in each place separately. Instead, you could create a variable: `val size = 60` and then use it in all places this way: `move(size)`. This way, changing the size of the drawing would require changing only one line: writing `val size = 120` instead of `val size = 60`.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/26"></iframe>

Another way of creating a variable is `var size = 60`, which differs from the previous one in the first word - it's `var` instead of `val`. If a variable is declared as a `var`, it means that it's value can be changed during the execution of a program:

```scala
var size = 20
(...)
size = 30
```

This would not be possible if a variable was a `val`.

We might also want to base the new value of a variable on its previous value. For example `size = size + 10` would increase the variable `size` by ten. The same thing can be written as `size += 10`. You could also use `*` for multiplying instead of increasing, `-` for decreasing or `/` for dividing.

### Example

Let's create a beginning of a square spiral. We'll start with a segment of length 10 and 90 degrees rotation and repeat that a few times, extending the length of each next segment by 10.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/50"></iframe>

## Conditionals

Sometimes we might want to perform some action depending on some condition. This is where conditional statements come in handy. Conditions are boolean statements - in our case they can be based on some properties of numerical variables such as for example:

* `n > 5` - true if variable `n` is greater than 5,
* `n >= 5` - true if `n` is greater than or equals 5,
* `n < 5` - true if `n` is smaller than 5,
* `n <= 5` - true if `n` is smaller than or equals 5,
* `n == 5` - true if `n` equals 5,
* `n != 5` - true if `n` does not equal 5,
* `n % 2 == 0` - true if `n` is even,
* `n % 2 != 0` - true if `n` is odd.

We might want to check more than one condition:

* if we want all of given conditions to be true, we combine them with `&&` - e.g.: `a == 1 && b == 2 && c == 3`,
* if we want at least one of given conditions to be true, we combine them with `||` - e.g.: `a == 1 || b == 2 || c == 3`.

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

Another possibility is that if the first condition is false we want to check another one. And if that one is also false we want to check yet another one and so on. This can be achieved by writing the following:

```scala
if (condition1) {
  //code A
} else if (condition2) {
  //code B
} else if (condition3) {
  //code C
} else {
  //code D
}
```

In the sample above:

* if `condition1` is true, "code A" will be executed,
* if `condition1` is false but `condition2` is true, "code B" will be executed,
* if both `condition1` and `condition2` are false but `condition3` is true, "code C" will be executed,
* if all `condition1`, `condition2` and `condition3` are false, "code D" will be executed.

It might also be worth mentioning that the last `else {...}` is optional - we don't have to write it if we don't want to execute anything if all `condition1`, `condition2` and `condition3` are false. Then the code would look like this:

```scala
if (condition1) {
  //code A
} else if (condition2) {
  //code B
} else if (condition3) {
  //code C
}
```

Let's use conditionals in the example below to create a triangle - a green one if the size is greater than 100, a red one otherwise. Try changing the value of `size` and see the result.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/47"></iframe>

It is also possible to depend a value assinged to a variable on some condition in a very concise way like this: `val s = if (n >= 0) n else -n`. This snippet assigns the value of `n` to `s` if `n` is non-negative and the opposite number (`-n`) if `n` is negative - either way, the value of `s` won't be negative.

We will use it in the example below - it's very similar to the previous one, take a look.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/28"></iframe>

## Loops

Very often we want to execute the same (or similar) piece of code consecutively. The simplest way to achieve this is:

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

In the example above "code A" will be repeated 5 times and "code B" will be repeated 5 + 2 = 7 times.

The `repeat` construct allows only simple repetition. We would be able to use it in our example for drawing a square spiral but it would be better to use a `for` loop.

```scala
for(i <- 1 to 10) {
  move(i * 10)
  rotate(90)
}
```

In this example the code inside braces will be executed 10 times. Why? Because of `i <- 1 to 10` - this means that during each subsequent execution of the code in a loop the variable `i` will have different value: starting with 1, then 2, 3, and so on, and finally 10, which together makes ten times! As a result we will draw ten sides of a spiral - with lengths 10, 20, 30, ..., 100 respectively.

There are various other forms of `for` loops in Scala, however we won't go into further details about them.

Another similar construct is a `while` loop.

```scala
while(condition) {
  //put code here
}
//some other code
```

The `condition` here can be any statement with a boolean value (see the "Conditionals" section above). The execution goes as follows:

 1. the condition is evaluated  
  1.a. if it's false, all the code in braces is omitted and the execution moves to "some other code"  
  1.b. if it's true, the code in braces is executed and then **we go back to point 1.* (condition evaluation)

In the example below you can see how the `while` loop was used for creating the quadratic spiral until the length of the side was larger than 150.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/29"></iframe>

### Excercises:

1. Create similar triangle spirals but starting from the longest segment. Do it using:

* `repeat` ([&#8594;](/en/solutions#ex2.1.a)) 
* `for` ([&#8594;](/en/solutions#ex2.1.b))
* `while` ([&#8594;](/en/solutions#ex2.1.c))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Back to home page](/en)

[Previous: Introduction](/en/1_introduction)  
[Next: Functions](/en/3_functions)