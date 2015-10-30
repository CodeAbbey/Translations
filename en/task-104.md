Being able to calculate area of triangle is quite important since many more complex tasks are often easily reduced to
this (and we will use it too later).

One of the oldest known methods is [Heron's Formula](http://en.wikipedia.org/wiki/Heron's_formula) which takes as inputs
the lengths of the triangle's sides.

In this problem you however is to write a program which uses `X` and `Y` coordinates of the triangle's vertices instead.
So you can use either this formula somehow or find another one.

**Input data** will contain the number of triangles to process.  
Next lines will contain `6` values each, in order `X1 Y1 X2 Y2 X3 Y3`, describing three vertices of a triangle.  
**Answer** should give areas of triangles separated by space (precision about `1e-7` is expected).

Example:

    data:
	3
	1 3 9 5 6 0
	1 0 0 1 10000 10000
	7886 5954 9953 2425 6250 2108
	
	answer:
	17 9999.5 6861563
