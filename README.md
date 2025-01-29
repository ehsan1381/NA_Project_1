# Description
This repository is a submitted answer to an assignment in a numerical analysis course. The problem is
very simple. The sequence of functions with the bellow relation is given and we are asked to provide
a recurrence relation and a program written in MATLAB which generates the sequence, given inputs $n$
and $a$. $\int_0^1{\frac{x^{2n}}{x^2 + a}}dx$

# Solution
With a simple algebraic manipulation we have $\frac{1}{2n-1} - a I_{n-1}$. Now this relation will have some issues if
used in numerical computations. Since this integral only exists if $a \not\in [-1, 1]$  the term $aI_{n-1}$ will magnify
any error in computation of $I_{n-1}$ and is also added to the next terms. This makes the algorithm
unstable. To get around this issue we will solve this relation for term $I_{n-1}$ and obtain a backwards
relation. The program will then be very simple.

# Program Walk through
We first validate arguments and set some default values for input arguments. Then we have two
checks. First for convergence and then if argument `n` is an integer. We take it as a double because
of how MATLAB handles operations which contain doubles and integers. The rest of the program is as
simple as it gets.
