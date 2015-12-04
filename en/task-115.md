We are already acquainted with the [gradient calculation](./gradient-calculation) for arbitrary math functions.
Let us learn how to apply this knowledge!

**Gradient descent** is a popular method of optimization - it works like following:

1. We have a **target** function of the form `f(x1, x2, ... , xn)` - and want to optimize (e.g. minimize) its value by
    finding the best suit of `xi` values.
2. Probe the gradient of this function at some random point `(x1, x2, ... , xn)`.
3. This gradient shows as the direction (as a vector `(dx1, dx2, ... , dxn)` in which the function grows most speedily.
4. Let us make a step in the opposite direction and change the set of `xi` values accordingly.
5. Calculate new value of the function and if we are not satisfied, repeate with the new point from the step `2`.

We'll implement this algorithm for solving
[System of Linear Equations](http://en.wikipedia.org/wiki/System_of_linear_equations) - extremely popular task which
is encountered in many fields, like business predictions (and other machine learning), graphics, physics etc.

System of `n` equations with `n` variables is generally represented like:

    a11 * x1  +  a12 * x2  +  ...  +  a1n * xn  =  b1
    a21 * x1  +  a22 * x2  +  ...  +  a2n * xn  =  b2
       ...          ...                  ...       ...
    an1 * x1  +  an2 * x2  +  ...  +  ann * xn  =  bn

The solution of it is such a vector of `[x1, x2, ... , xn]` for which equations become true - i.e. for which the left
parts becomes equal to right ones.

Let us construct the **target** function in the following way:

    f1  =  a11 * x1  +  a12 * x2  +  ...  +  a1n * xn  -  b1
    f2  =  a21 * x1  +  a22 * x2  +  ...  +  a2n * xn  -  b2
       ...          ...                  ...       ...
    fn  =  an1 * x1  +  an2 * x2  +  ...  +  ann * xn  -  bn
	
	f(x1, x2, ... , xn)  =  f1 * f1  +  f2 * f2  +  ...  +  fn * fn

i.e. it is the **sum of squares** of the differences between left and right parts for each of equations. Obviously
the minimum of this function is `0` and it is reached when the vector of `x`-s equals to solution of the system.

---

###Algorithm

You will need to understand and implement the proposed algorithm for the **gradient descent** of the target function.
Below is the description in pseudocode. Your goal is to count how many iteration algorithm performs before finishing.

    X = [0, 0, ... , 0]        # solution vector [x1, x2, ... , xn] is initialized with zeroes
	
	STEP = 0.01                # step of the descent - it will be adjusted automatically
	ITER = 0                   # counter of iterations
	
	WHILE (true)
	    Y = F(X)               # calculate the target function at the current point
		IF (Y < 0.0001)        # condition to leave the loop
		    BREAK
		END IF
			
	    DX = STEP / 10         # mini-step for gradient calculation
		G = CALC_GRAD(X, DX)   # G(x1, x2, ... , xn) just as in "gradient calculation" problem
		
		XNEW = X               # copy the current X vector
		FOR (i = 1 .. n)       # and make the step in the direction specified by the gradient
		    XNEW[i] -= G[i] * STEP
		END FOR
		
		YNEW = F(XNEW)         # calculate the function at the new point
		IF (YNEW < YN)         # if the new value is better
		    X = XNEW           # shift to this new point and slightly increase step size for future
		    STEP = MIN(0.1, STEP * 1.25)
	    ELSE                   # if the function value grows it means step was too large
		    STEP = STEP / 1.25
		END IF
		
		ITER += 1              # increment iteration counter
	END WHILE

So we end the descent when the value of target function becomes small enough (less than `0.0001`) and return the
number of iterations.

**To calculate gradient** of the function at the given point `x1, x2, ... , xn` we need to calculate its values
at `N` neighboring points, each of the "staying aside" by the value `dx` along one of coordinate axes:

    y = f(x1, x2, ... , xn)
	
	y1 = f(x1 + dx, x2, ... , xn)
	y2 = f(x1, x2 + dx, ... , xn)
	  ...
	yn = f(x1, x2, ... , xn + dx)

After which the vector representing the gradient is composed like following:

    g1 = (y1 - y) / dx
	g2 = (y2 - y) / dx
	  ...
	gn = (yn - y) / dx
	
	g = [g1, g2, ... , gn]

If you recollect "gradient calculation" problem - there we had letters `f` instead of `y` and `x, y` instead of
`x1, x2`. (*however for given task it is impractical to name many coordinates with separate letters, so we use
`x` with indexes*)

###Example

Below is an example of first iterations for sample system with `N = 3`:
	
	Matrix of coefficients "aij":
	8 -1 -8
	-4 2 9
	-8 -9 2
	
	Vector of right sides "bi":
	9 -5 -7
	
	"x1", "x2", "x3" and "step" on each iteration:
	0:  0.00000 0.00000 0.00000   step: 0.01
	1:  0.00000 0.00000 0.00000   step: 0.008
	2:  0.00000 0.00000 0.00000   step: 0.0064
	3:  0.00000 0.00000 0.00000   step: 0.00512
	4:  0.00000 0.00000 0.00000   step: 0.004096
	5:  0.00000 0.00000 0.00000   step: 0.0032768
	6:  0.96977 0.28826 -0.85868  step: 0.004096
	7:  0.96977 0.28826 -0.85868  step: 0.0032768
	8:  0.26577 0.10317 -0.15674  step: 0.004096
	9:  0.26577 0.10317 -0.15674  step: 0.0032768
	10: 0.82771 0.24396 -0.66572  step: 0.004096
	11: 0.82771 0.24396 -0.66572  step: 0.0032768

---

**Input data** will contain the number of systems to solve in the first line.  
For each system there would be the description of several lines.  
At the beginning the amount of equations / variables (`N`) is specified.  
Then `N` lines with `N` coefficients `aij` follow.  
The last line of the section contains the vector of `N` values of `bi`.  
**Answer** should contain the amount of steps for the given algorithm to finish, for each case. We allow these
answers have a small error of `+/- 2` or `5%` of the required value (which is greater).

Example:
	
	input data:
	4                # number of systems to solve
	3                # the first system is of 3*3 size
	-9 2 -1          # 3 lines with coefficients follow
	1 -3 0
	-3 -1 -7
	-2 4 3           # the vector of right side values
	4                # the second system is of 4*4 size
	0 -4 -1 6        # and so on...
	7 7 6 9
	-6 3 -7 8
	-7 -5 1 -4
	1 9 -2 9
	3
	9 4 -8
	-8 1 7
	-6 -3 -8
	6 4 6
	5
	6 5 -9 2 -1
	-4 -6 -6 -6 8
	7 6 4 2 -9
	-2 -3 -9 -7 -5
	-8 2 8 -7 -5
	-2 -1 -2 1 3
	
	answer:
	101 114 178 279
