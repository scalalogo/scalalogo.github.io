---
layout: default
---

[Back to table of contents](/en)  
[Previous: Variables, conditionals and loops](/en/2_language_basics)  
[Next: Recursion](/en/4_recursion)  

## Functions

Functions are samples of code that can be called by their name for execution. See the example below including two function definitions.

TODO iframe

First of all if you try to run the app, you will see that nothing is being drawn - this is because the code consists of only two function definitions and we have to call them to make them execute. How do you call a function? This is easy and you already know it! Every time you write `move(...)` or `rotate(...)` or `up()`/`down()` etc. you call a function. So here it would be as simple as writing `move40andRotate90()` or `moveAndRotate(40, 90)`.

As you have probably noticed sometimes in addition to the name of the function you can also pass some values (called parameters or arguments) in parentheses. This depends on how the function is defined. Let's take a look at the first function definition. It starts with a `def` word which indicates start of the function definition. Then there is the name of the function followed by empty parentheses, then the equals sign and finally braces enclosing the so called body of the function i.e. lines of code that will be executed when the function is called.

The second definition differs from the first one - the parentheses contain something that is called parameter list. This list defines how many values should be passed when the function is called and what types they should have (e.g. integer `Int`, decimal `Double` or `Float`, text `String`). In our case we can see that two arguments should be passed to the `moveAndRotate` function and both of them should be decimal. Now, let's see how the arguments are used inside the body of the function. They are simply treated like any other variable in the scope. The only difference is that it's value is not defined here - it will depend on the value passed to the function (and each time the function is called this value can be different). To be precise, the arguments are treated as `val` variables, so if you have a parameter named `size` you won't be able to assign another value to it (e.g. decrease it by 2: `size = size - 2`)

### Excercises:

1. Play with the example with functions definition - call them, perhaps a few times, try passing various parameters to the function that takes them.
2. Define a function for drawing a square taking one parameter - side length. Try to make the body of the function shorter than 4 lines of code (see the "Loops" section in the previous chapter). Use the function to draw a big square with a few smaller squares inside of it.
3. \* Write a function drawing a regular polygon. It should get two arguments: number of sides and length of side.

secion about return type?

<iframe height="600" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/8"></iframe>

[Back to table of contents](/en)  
[Previous: Variables, conditionals and loops](/en/2_language_basics)  
[Next: Recursion](/en/4_recursion)