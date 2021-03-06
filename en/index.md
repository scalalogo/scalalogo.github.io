---
layout: default
---

# Welcome to ScalaLogo!

On this page you will learn basics of programming in a fun way. The tutorials are inspired by the [Logo programming language](https://en.wikipedia.org/wiki/Logo_(programming_language)) adapted to [Scala](https://www.scala-lang.org/). This way you can get a grasp of a modern, popular programming language by having fun creating turtle graphics!

The turtle graphics is a popular way for introducing programming to kids. The turtle is like a small robot (represented as a triangle) that moves according to your commands and leaves a trace so you can use it to draw whatever you want!

## Overview

The tutorials are based on a mini-library written in Scala that was created to enable drawing turtle graphics in a way similar to Logo. They are enriched with live examples thanks to [ScalaFiddles](https://scalafiddle.io/). Each example has a sample of code that will be run - you can see the result right next to the code. However, nothing will happen, until you tell it to. Below the drawing plane you can see a few management buttons with which you can:

* adjust how long it takes to make one action next to <i class="fa fa-clock-o"></i> (the higher the number is, the slower the turtle moves),
* make the turtle move consecutively (according to the code on the left) with <i class="fa fa-play"></i> or stop it with <i class="fa fa-pause"></i>,
* make it perform a single action (move, rotation, etc.) with <i class="fa fa-step-forward"></i>,
* show or hide it with <i class="fa fa-low-vision"></i>.

The code is editable. If you make any changes to it or just want to run it once again, click the _Run_ button above the code. You can always restore the code to its original version with the _Reset_ button. This will only revert the code changes - if you want to reset tha application as well, click the _Run_ button.

After running the code you might get a message in English like this: _Too many actions!_. This means that your code created more actions to perform than allowed. If you see it, most probably you have created an infinite loop or an infinite recursion (you'll learn about loops and recursion in further chapters).

## Table of contents

1. [Introduction](/en/1_introduction)
2. [Variables, conditionals and loops](/en/2_language_basics)
3. [Functions](/en/3_functions)
4. [Recursion](/en/4_recursion)

<iframe height="620" frameborder="0" style="width: 100%; overflow: hidden;" src="https://embed.scalafiddle.io/embed?sfid=okXrWZp/22"></iframe>