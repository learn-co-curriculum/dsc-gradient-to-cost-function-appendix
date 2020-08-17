
# Gradient to Cost Function - Appendix

## Introduction

In this lesson, you'll find the details on how to compute the partial derivatives in the "Gradient to cost function" lesson.

## Computing the First Partial Derivative

Let's start with taking the **partial derivative** with respect to  <img src="https://render.githubusercontent.com/render/math?math=m"> .

<img src="https://render.githubusercontent.com/render/math?math=\frac{\delta J}{\delta m}J(m, b) = \frac{\delta J}{\delta m}(y - (mx %2b b))^2"> 

Now this is a tricky function to take the derivative of.  So we can use functional composition followed by the chain rule to make it easier.  Using functional composition, we can rewrite our function  <img src="https://render.githubusercontent.com/render/math?math=J"> as two functions: 

<img src="https://render.githubusercontent.com/render/math?math=g(m,b) = y - (mx %2b b)\mspace{5ex}"> -- set <img src="https://render.githubusercontent.com/render/math?math=g"> equal to <img src="https://render.githubusercontent.com/render/math?math=y-\hat{y}">

<img src="https://render.githubusercontent.com/render/math?math=J(g(m,b)) = (g(m,b))^2\mspace{4ex}"> -- now  <img src="https://render.githubusercontent.com/render/math?math=J"> is a function of  <img src="https://render.githubusercontent.com/render/math?math=g"> and  <img src="https://render.githubusercontent.com/render/math?math=J=g^2"></center>

Now using the chain rule to find the partial derivative with respect to a change in the slope, gives us:

<img src="https://render.githubusercontent.com/render/math?math=[1]\mspace{5ex}\frac{dJ}{dm}J(g) = \frac{dJ}{dg}J(g(m, b))*\frac{dg}{dm}g(m,b)"> 

Because **g** is a function of **m** we get  <img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\frac{dg}{dm}}(g)"> and 

**J** is a function of **g (which is a function of m**) we get  <img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\frac{dJ}{dg}}(J)"> .

Our next step is to solve these derivatives individually.

First:

<img src="https://render.githubusercontent.com/render/math?math=\frac{dJ}{dg}J(g(m, b)) =\frac{dJ}{dg}g(m,b)^2">

Solve <img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\frac{dJ}{dg}}(J)"> :

<img src="https://render.githubusercontent.com/render/math?math=\frac{dJ}{dg}J(g(m, b)) = 2*g(m,b)">

Then:

<img src="https://render.githubusercontent.com/render/math?math=\frac{dg}{dm}g(m,b) =\frac{dg}{dm} (y - (mx %2bb))">

Solve <img src="https://render.githubusercontent.com/render/math?math=\boldsymbol{\frac{dg}{dm}}(g)">:

<img src="https://render.githubusercontent.com/render/math?math=\frac{dg}{dm}g(m,b) =\frac{dg}{dm} (y - mx - b)"> 
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{9ex}=\frac{dg}{dm}y - \frac{dg}{dm}mx - \frac{dg}{dm}b">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{9ex}= 0-x-0">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{9ex}=-x">

> Each of the terms are treated as constants, except for the middle term.  

Now plugging these back into our chain rule [1] we have: 

<img src="https://render.githubusercontent.com/render/math?math=\color{blue}{\frac{dJ}{dg}J(g(m,b))}\color{black}{*}\color{red}{\frac{dg}{dm}g(m,b)} \color{black}{=}\color{blue}{(2*g(m,b))}\color{black}{*}\color{red}{-x}">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{21.75ex}= 2*(y - (mx %2b b))*-x">

So
 
<img src="https://render.githubusercontent.com/render/math?math=[1]\mspace{5ex}\frac{\delta J}{\delta m}J(m, b) =2*(y - (mx %2b b))*-x">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{15.75ex}= -2x*(y - (mx %2b b ))"> 

## Computing the Second Partial Derivative

Ok, now let's calculate the partial derivative with respect to a change in the y-intercept.  We express this mathematically with the following:

 <img src="https://render.githubusercontent.com/render/math?math=\frac{\delta J}{\delta b}J(m, b) = \frac{dJ}{db}(y - (mx %2b b))^2"> 

Then once again, we use functional composition following by the chain rule.  So we view our cost function as the same two functions  <img src="https://render.githubusercontent.com/render/math?math=g(m,b)"> and  <img src="https://render.githubusercontent.com/render/math?math=J(g(m,b))"> .  

 <img src="https://render.githubusercontent.com/render/math?math=g(m,b) = y - (mx %2b b)"> 

 <img src="https://render.githubusercontent.com/render/math?math=J(g(m,b)) = (g(m,b))^2"> 

So applying the chain rule, to this same function composition, we get:

 <img src="https://render.githubusercontent.com/render/math?math=[2]\mspace{5ex}\frac{dJ}{db}J(g) = \frac{dJ}{dg}J(g)*\frac{dg}{db}g(m,b)"> 

Now, our next step is to calculate these partial derivatives individually.

From our earlier calculation of the partial derivative, we know that  <img src="https://render.githubusercontent.com/render/math?math=\frac{dJ}{dg}J(g(m,b)) = \frac{dJ}{dg}g(m,b)^2 = 2*g(m,b)"> .  

The only thing left to calculate is  <img src="https://render.githubusercontent.com/render/math?math=\frac{dg}{db}g(m,b)">:

<img src="https://render.githubusercontent.com/render/math?math=\frac{dg}{db}g(m,b) =\frac{dg}{db}(y - (mx %2b b) )">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{8.5ex}=\frac{dg}{db}(y-mx-b)">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{8.5ex}=\frac{db}{db}y-\frac{db}{db}mx-\frac{dg}{db}b">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{8.5ex}=0-0-1">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{8.5ex}= -1">

Now we plug our terms into our chain rule [2] and get: 

<img src="https://render.githubusercontent.com/render/math?math=\color{blue}{\frac{dJ}{dg}J(g)}\color{black}{*}\color{red}{\frac{dg}{db}g(m,b)} \color{black}{=} \color{blue}{2*g(m,b)}*\color{red}{-1}">
<br>
<img src="https://render.githubusercontent.com/render/math?math=\mspace{16ex}=-2*(y - (mx %2b b))">

