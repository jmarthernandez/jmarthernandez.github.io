---
layout: post
title:  "Elimnation with Matrices"
subtitle: "Solving Systems of Equations with Matrices"
date:   2015-11-13
categories: [linear_algebra]
---
___

 This post assumes you know about basic matrix operations.  If you need to review those check this [previous post]({% post_url 2015-11-13-matrices %})

___

# Elimination

Elimnation is used for solving systems of equations.  

The following system can be represented by matrices.

$$
\begin{align}
  x + 2y + z & = 2\\
  3x + 8y + z & = 12\\
  4y + z & = 2
\end{align}
$$

Let's pick apart the equation $$Ax = B$$.  $$A$$ is a coefficient matrix.
What this means is that the coefficients from the systems are stored here.
The $$x$$ is a vector that contains all the variables $$x, y, z$$.  The matrix
$$B$$ is contains everything to the left of the equals sign.

$$
  A=
  \begin{bmatrix}
  1 & 2 & 1 \\
  3 & 8 & 1 \\
  0 & 4 & 1 \\
  \end{bmatrix}
,\,\, x=
  \begin{bmatrix}
  x\\
  y\\
  z\\
  \end{bmatrix}
,\,\, B=
  \begin{bmatrix}
  2\\
  12\\
  2\\
  \end{bmatrix}
$$

Our goal is go from this

$$
  \begin{bmatrix}
  1 & 2 & 1 \\
  3 & 8 & 1 \\
  0 & 4 & 1 \\
  \end{bmatrix}
  \begin{bmatrix}
  x\\
  y\\
  z\\
  \end{bmatrix}
  =
  \begin{bmatrix}
  2\\
  12\\
  2\\
  \end{bmatrix}
$$ 

to 

$$
  \begin{bmatrix}
  1 & 2 & 1 \\
  0 & 2 & -2 \\
  0 & 0 & 5 \\
  \end{bmatrix}
  \begin{bmatrix}
  x\\
  y\\
  z\\
  \end{bmatrix}
  =
  \begin{bmatrix}
  2\\
  6\\
  -10\\
  \end{bmatrix}
$$

which is the same as

$$
\begin{align}
  x + 2y + z & = 2\\
  2y + -2z & = 6\\
  5z & = -10
\end{align}
$$

What we end up with is an upper triangle matrix.  All the values below the diagonal are 
zero which makes substitution trivial because $$z$$ is solved.

The way we change indices to $$0$$ is by adding and subtracting rows from each other
like we would with a typical system of equations.

We are going to drop the $$x$$ vector and incorporate it later. Lets start by adding $$-3$$ of the first row to the second row.

$$
  \left[
    \begin{array}{ccc|c}
    1      & 2      & 1 & 2\\
    3 + -3(1) & 8 + -3(2) & 1 + -3(1) & 12 + -3(2)\\
    0      & 4      & 1 & 2\\
    \end{array}
  \right]
$$ 

We are now left with the second row without an $$x$$ coefficient.

$$
  \left[
    \begin{array}{ccc|c}
      1 & 2 & 1 & 2\\
      0 & 2 & -2 & 6\\
      0 & 4 & 1 & 2\\
    \end{array}
  \right]
$$ 

Now lets add $$-2$$ of the second row to the third row.

$$
  \left[
    \begin{array}{ccc|c}
      1 & 2 & 1 & 2\\
      0 & 2 & -2 & 6\\
      0 & 0 & 5 & -10\\
    \end{array}
  \right]
$$

With this matrix it is easy to see that $$z = -2$$.  Knowing that, back substitution is trivial.
