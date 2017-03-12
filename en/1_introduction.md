---
layout: default
---

[Back to Table of contents](/en)  
[Next: Variables, conditionals and loops](/en/2_language_basics)  

## Introduction

The general idea is that there is a "turtle" that can move on an area drawing lines in various colors and directions. First, let's take a look at the basic actions that are available in the application.

* `move(steps)` moves the turtle for a given amount of steps. If the number of steps is negative, the turtle moves backwards.
* `rotate(angle)` rotates the turtle by a given angle (in degrees, with positive values treated as clockwise). For example: turning right by a right angle could be achieved by `rotate(90)`, turning alike but left would be `rotate(-90)` or `rotate(270)`, whereas changing the direction to the opposite one could be either `rotate(180)` or `rotate(-180)`
* `up()` takes the turtle up. If the turtle is up it doesn't draw lines when moving.
* `down()` puts the turtle down so that it can draw lines again.
* `show()` makes the turtle visible.
* `hide()` hides the turtle from view. Visibility of the turtle does not influence drawing in any way.
* `setColor(color)` changes the color of lines drawn by the turtle. You can use a set of predefined colors (white, silver, gray, black, red, maroon, yellow, olive, lime, green, aqua, teal, blues, navy, fuchsia, purple) or create your own. For the former option you simply write `setColor(Color.Blue)`. The latter option is used as following: `setColor(Color(30, 40, 50))`, where 30, 40 and 50 stand for red, green and blue respectively, in the range 0 to 255 (for more information on RGB color model see [here](https://en.wikipedia.org/wiki/RGB_color_model).
* setInterval(interval) changes how long it takes to perform one action.
* write(something) can be used for debugging purposes. It will show a textual representation of whatever is passed as `something` under the management buttons. 

In addition, any line starting with `//` is a so called comment - it isn't treated as a code and doesn't get executed.

### Example

Let's say we want to draw a regular hexagon but in a special way - we only draw every second side, each in a different color.

<iframe height="600" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/23"></iframe>

### Excercises:

1. Draw a regular octagon in a similar way (only every second side and each in a different color).  
    Hint: You will have to change the rotation angle!

    [link](https://scalafiddle.io/sf/okXrWZp/24)
2. Draw a star pentagon.

	[link](https://scalafiddle.io/sf/okXrWZp/25)

<iframe height="600" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/48"></iframe>

[Back to Table of contents](/en)  
[Next: Variables, conditionals and loops](/en/2_language_basics)