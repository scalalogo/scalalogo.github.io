---
layout: default
---

[Back to home page](/en)

[Previous: Functions](/en/3_functions)

## Recursion

Keep in mind that this chapter is much more advanced than the others so don't worry if it becomes hard for you.

Recursion occurs when the function calls itself inside of its body. Let's start with a non-graphical example. We'll write a recursive function for calculating a sum of integer numbers from `0` to given `n`. Remember that we do this just to help you understand the concept as this can (and normally should) be done without recursion. You can write such a function as an excercise, below you can see a recursive version. Another thing that should be mentioned here is that in case of recursive functions, Scala requires you to explicitly declare the return type.

```scala
def sum(n: Int): Int = {
  if (n <= 0) 0 else n + sum(n - 1)
}
```

Suppose we call this function with the argument of value `2`. Then it would be calculated as follows:

```
sum(2) = 2 + sum(1) = 2 + 1 + sum(0) = 2 + 1 + 0 = 3
```

What's very important is that the recursion has to stop somewhen. This means that we cannot call the function recursively all the time, unconditionally. In the example if the argument is 0 we simply return 0. Only for positive arguments we actually create recursion (with argument decreased by 1) to get the sum from `0` to `n - 1` and return it increased by `n`.

Now let's try to use a simple recursion for creating some graphics. Again, we'll draw a square spiral, but this time we'll do it starting with the longest segment.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/36"></iframe>

Recursion in graphics is often used to create [fractals](https://en.wikipedia.org/wiki/Fractal). Here you can see an example of a tree:

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/38"></iframe>

And this is a [Barnsley fern](https://en.wikipedia.org/wiki/Barnsley_fern):

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/41"></iframe>

### Excercises

1. Draw a [Sierpinski carpet](https://en.wikipedia.org/wiki/Sierpinski_carpet). ([&#8594;](/en/solutions#ex4.1))
2. Draw a [Sierpinski triangle](https://en.wikipedia.org/wiki/Sierpinski_triangle). ([&#8594;](/en/solutions#ex4.2))
3. Draw a [Koch snowflake](https://en.wikipedia.org/wiki/Koch_snowflake). ([&#8594;](/en/solutions#ex4.3))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/49"></iframe>

[Back to home page](/en)

[Previous: Functions](/en/3_functions)