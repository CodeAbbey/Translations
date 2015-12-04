<!-- #Binary Search -->
Programming of Binary Search is the common task since it is used for searching through sorted arrays (that's why we
learnt sorting) as well as for solving math equations. Let us practice the latter application. Please kindly refer
to the [Binary Search article][wiki] for thorough explanations if you feel not well acquainted with the idea
of the algorithm.

[wiki]: ../wiki/binary-search

The goal is to solve the equation which has the following form:

    A * x + B * sqrt(x ^ 3) - C * exp(-x / 50) - D = 0

here `A`, `B` and `C` all would be positive so that function is monotonic. Solution is guaranteed to exist
somewhere in range `0 <= x <= 100`.

Solution should be calculated with precision `0.0000001 = 1e-7` or better.

**Input data** will contain number of test-cases in the first line.  
Next lines will contain four numbers for each test-case, i.e. `A B C D` separated by values.  
**Answer** should contain solutions - i.e. values of `x` which satisfy equation with given coefficents - several
answers (for several test-cases) should be separated with spaces.

Example:
	
	input data:
    2
    0.59912051 0.64030348 263.33721367 387.92069617
    15.68387514 1.26222280 695.23706506 698.72384731
	
	answer:
	73.595368554162 41.899174957955

You may also want to try the [Binary Search in Array](./binary-search-in-array) problem - even more popular
use-case for this algorithm!