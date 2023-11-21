---
layout: posts
title: fractals

---

## Triangle Fractal In Python

<body>
    <br>
    <h4>
        STEP 1:
        <br>
        IMPORTING LIBRARY
    </h4>
    <pre>
import turtle
        </pre>
    <h4>
        STEP 2:
        <br>
        DEFINING TRIANGLE FUNCTION
    </h4>
    <pre>
def triangle(s):
    turtle.pencolor("#a5cbe2")
    turtle.pensize(2)
    turtle.forward(s)
    turtle.left(120)
    turtle.forward(s)
    turtle.left(120)
    turtle.forward(s)
    turtle.left(120)
    
</pre>
    <h4>
        STEP 3:
        <br>
        DEFINING FRACTAL FUNCTION
    </h4>
<pre>
def fractal(n, s):
    if n == 0:
        triangle(s)
    else:
        turtle.fillcolor("#74a7d2")
        turtle.begin_fill()
        fractal(n-1, s/2)
        turtle.end_fill()
        turtle.forward(s/2)
        turtle.fillcolor("#3b7fb9")
        turtle.begin_fill()
        fractal(n-1, s/2)
        turtle.end_fill()
        turtle.left(120)
        turtle.forward(s/2)
        turtle.right(120)
        turtle.fillcolor("#234c6f")
        turtle.begin_fill()
        fractal(n-1, s/2)
        turtle.end_fill()
        turtle.right(120)
        turtle.forward(s/2)
        turtle.left(120)
</pre>
    <h4>
        FINAL STEP:
        <br>
        RUNNING THE CODE
    </h4>
    <pre>
turtle.tracer(0)
fractal(5, 400)
turtle.update()
turtle.mainloop()

</pre>
    <h4>
        FINAL RESULT
    </h4>
<img src="../assets/images/triangle.png">

## Tree Fractal
<h4>
    STEP 1:
    <br>
    IMPORTING LIBRARY
</h4>
    <pre>
import turtle
        </pre>
<h4>
    STEP 2:
    <br>
    DEFINING LEAF FUNCTION
</h4>
<pre>
def leaf():
    turtle.pencolor("#0f6401")
    turtle.fillcolor("#1fc803")
    turtle.begin_fill()
    turtle.left(30)
    turtle.forward(9)
    turtle.right(60)
    turtle.forward(9)
    turtle.right(120)
    turtle.forward(9)
    turtle.right(60)
    turtle.forward(9)
    turtle.right(150)
    turtle.forward(9 * (3 ** 0.5))
    turtle.backward(9 * (3 ** 0.5))
    turtle.end_fill()
        </pre>
    <h4>
        STEP 3:
        <br>
        DEFINING TREE FUNCTION
    </h4>
    <pre>
def tree(d, r, w):
    if d < 7 or r < 7:
        return
    turtle.pensize(w)
    turtle.forward(d)
    turtle.left(r)
    tree(d * 0.7, r, w*0.6)
    if d > 7 and d < 9:
        leaf()
    turtle.right(2 * r)
    tree(d * 0.7, r, w*0.6)
    turtle.left(r)
    turtle.backward(d)
    turtle.pencolor("#ab6b37")
        
        </pre>
    <h4 style="text-align: left;font-family: tahoma">
        FINAL STEP:
        <br>
        RUNNING THE CODE
    </h4>
<pre>
turtle.pencolor("#ab6b37")
turtle.speed(0)
turtle.left(90)
tree(100, 30, 10)
turtle.mainloop()
</pre>
<h4>
    FINAL RESULT
</h4>
<img src="../assets/images/tree.png">

## Jungle

- for making a jungle in python first of all we need two functions: one for trees and another one for bushes.then we use random library to print our trees and bushes in random places.we can use variables to organizie them so we'll get a better result in the end

- here is an example of using variables:

<pre>
for n in range(12):
    x1 = -480 + (n*80)
    x2 = -480 + ((1+n)*80)
    turtle.penup()
    turtle.setpos(random.randint(x1, x2), random.randint(-170, -120))
    turtle.pendown()
    tree(110, 40, 20, 2)
</pre>
<img src="../assets/images/jungle2.png">