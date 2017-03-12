---
layout: default
---

[Back to table of contents](/en)

[Previous: Variables, conditionals and loops](/en/2_language_basics)

[Next: Recursion](/en/4_recursion)

## Functions

Functions are samples of code that can be called by their name for execution. See the example below including two function definitions.

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/33"></iframe>

First of all if you try to run the app, you will see that nothing is being drawn - this is because the code consists of only two function definitions and we have to call them to make them execute. How do you call a function? This is easy and you already know it! Every time you write `move(...)` or `rotate(...)` or `up()`/`down()` etc. you call a function. So here it would be as simple as writing `move40andRotate90()` or `moveAndRotate(40, 90)`.

As you have probably noticed sometimes in addition to the name of the function you can also pass some values (called parameters or arguments) in parentheses. This depends on how the function is defined. Let's take a look at the first function definition. It starts with a `def` word which indicates start of the function definition. Then there is the name of the function followed by empty parentheses, then the equals sign and finally braces enclosing the so called body of the function i.e. lines of code that will be executed when the function is called.

The second definition differs from the first one - the parentheses contain something that is called parameter list. This list defines how many values should be passed when the function is called and what types they should have. Some basic types would be:

* `Int` for integer,
* `Double` or `Float` for decimal,
* `String` for text,
* `Boolean` for true/false conditions.

In our case we can see that two arguments should be passed to the `moveAndRotate` function and both of them should be integers. Now, let's see how the arguments are used inside the body of the function. They are simply treated like any other variable in the scope. The only difference is that it's value is not defined here - it will depend on the value passed to the function (and each time the function is called this value can be different). To be precise, the arguments are treated as `val` variables, so if you have a parameter named `size` you won't be able to assign another value to it (e.g. decrease it by 2: `size = size - 2`)

### Excercises:

1. Play with the example with functions definition - call them, perhaps a few times, try passing various parameters to the function that takes them.
2. Define a function for drawing a square taking one parameter - side length. Try to make the body of the function as short as possible (see the "Loops" section in the previous chapter). Use the function to draw a big square with a few smaller squares inside of it. ([&#8594;](/en/solutions#ex3.2))
3. \* Write a function drawing a regular polygon. It should get two arguments: the number of sides and the length of a side. ([&#8594;](/en/solutions#ex3.3))

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/48"></iframe>

In our example, both functions had the purpose of performing some action. However, functions can also be used to perform some calculation and return a result that can be further used in the code. In general, Scala does not require defining the return type of the function (which was used in the example), but sometimes it might be necessary (see next chapter - "Recursion") and sometimes it's just a good practice, for code clarity. The return type of the function is defined between the parameter list and the body of the function. In case of functions that are supposed to perform actions and not return any value, the return type should be `Unit`. This means that we can change the definitions in the example by adding `: Unit` right after the parameter list, e.g.:

```scala
def moveAndRotate(...): Unit = {
  ...
}
```

Now let's see an example of a function that actually returns something meaningful. Remeber the `setColor` function? It takes one argument of type `Color`, which means we can also use it as a return type of a function. In Scala, the value of the last statement in the body of the function is returned.

```scala
def booleanToColor(b: Boolean): Color = {
  val c = if (b) Color.Red else Color.Green
  c
}
```

As you can see, we assign the red or green color (depending on the argument value) to the `c` variable and then we return `c`. There is no need to do that - an equivalent and more concise way to write this function would be:

```scala
def booleanToColor(b: Boolean): Color = {
  if (b) Color.Red else Color.Green
}
```

[Back to table of contents](/en)

[Previous: Variables, conditionals and loops](/en/2_language_basics)

[Next: Recursion](/en/4_recursion)