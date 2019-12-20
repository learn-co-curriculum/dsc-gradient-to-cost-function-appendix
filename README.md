
# Gradient to Cost Function - Appendix

## Introduction

In this lesson, you'll find the details on how to compute the partial derivatives in the "Gradient to cost function" lesson.

## Computing the First Partial Derivative

Let's start with taking the **partial derivative** with respect to $m$.

$$\frac{\delta J}{\delta m}J(m, b) = \frac{\delta J}{\delta m}(y - (mx + b))^2$$

Now this is a tricky function to take the derivative of.  So we can use functional composition followed by the chain rule to make it easier.  Using functional composition, we can rewrite our function $J$ as two functions: 

$$
\begin{align}
g(m,b)&= y - (mx + b) &&\text{set $g$ equal to $y-\hat{y}$}\\
\\
J(g(m,b))&= (g(m,b))^2 &&\text{now $J$ is a function of $g$ and $J=g^2$}\\
\end{align}
$$

Now using the chain rule to find the partial derivative with respect to a change in the slope, gives us:

$$
[1]\mspace{5ex}\frac{dJ}{dm}J(g) = \frac{dJ}{dg}J(g(m, b))*\frac{dg}{dm}g(m,b)
$$

Because **g** is a function of **m** we get $\boldsymbol{\frac{dg}{dm}}(g)$ and 

**J** is a function of **g (which is a function of m**) we get $\boldsymbol{\frac{dJ}{dg}}(J)$.

Our next step is to solve these derivatives individually: 
$$
\begin{align}
\frac{dJ}{dg}J(g(m, b))&=\frac{dJ}{dg}g(m,b)^2 &&\text{Solve $\boldsymbol{\frac{dJ}{dg}}(J)$}\\
\\
&= 2*g(m,b)\\
\\
\frac{dg}{dm}g(m,b)&=\frac{dg}{dm} (y - (mx +b)) &&\text{Solve $\boldsymbol{\frac{dg}{dm}}(g)$}\\
\\
&=\frac{dg}{dm} (y - mx - b)\\
\\
&=\frac{dg}{dm}y - \frac{dg}{dm}mx - \frac{dg}{dm}b\\
\\
&= 0-x-0\\
\\
&=-x\\
\end{align}
$$

> Each of the terms are treated as constants, except for the middle term.  

Now plugging these back into our chain rule [1] we have: 
$$
\begin{align}
\color{blue}{\frac{dJ}{dg}J(g(m,b))}*\color{red}{\frac{dg}{dm}g(m,b)}&=\color{blue}{(2*g(m,b))}*\color{red}{-x}\\
\\
&= 2*(y - (mx + b))*-x
\\
\end{align}
$$
 So
 
$$
\begin{align}
[1]\mspace{5ex}\frac{\delta J}{\delta m}J(m, b)&=2*(y - (mx + b))*-x\\
\\
&= -2x*(y - (mx + b ))\\
\end{align}
$$

## Computing the Second Partial Derivative

Ok, now let's calculate the partial derivative with respect to a change in the y-intercept.  We express this mathematically with the following:

$$\frac{\delta J}{\delta b}J(m, b) = \frac{dJ}{db}(y - (mx + b))^2$$

Then once again, we use functional composition following by the chain rule.  So we view our cost function as the same two functions $g(m,b)$ and $J(g(m,b))$.  

$$g(m,b) = y - (mx + b)$$

$$J(g(m,b)) = (g(m,b))^2$$

So applying the chain rule, to this same function composition, we get:

$$[2]\mspace{5ex}\frac{dJ}{db}J(g) = \frac{dJ}{dg}J(g)*\frac{dg}{db}g(m,b)$$

Now, our next step is to calculate these partial derivatives individually.

From our earlier calculation of the partial derivative, we know that $\frac{dJ}{dg}J(g(m,b)) = \frac{dJ}{dg}g(m,b)^2 = 2*g(m,b)$.  The only thing left to calculate is $\frac{dg}{db}g(m,b)$.

$$
\begin{align}
\frac{dg}{db}g(m,b)&=\frac{dg}{db}(y - (mx + b) )\\
\\
&=\frac{dg}{db}(y-mx-b)\\
\\
&=\frac{db}{db}y-\frac{db}{db}mx-\frac{dg}{db}b\\
\\
&=0-0-1\\
\\
&= -1\\
\end{align}
$$

Now we plug our terms into our chain rule [2] and get: 

$$
\begin{align}
\color{blue}{\frac{dJ}{dg}J(g)}*\color{red}{\frac{dg}{db}g(m,b)}&= \color{blue}{2*g(m,b)}*\color{red}{-1}\\
\\
&= -2*(y - (mx + b))\\
\end{align}
$$
