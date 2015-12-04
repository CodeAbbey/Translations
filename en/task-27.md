_It may be helpful to solve [Bubble in Array](./bubble-in-array) before this problem._

Array sorting is a popular problem for newcomers - and extremely important thing in professional
programming (in databases, libraries etc).

**Sorting** is reordering according to some simple rule based on comparison. Suppose we are given an array:

    a = [3, 1, 4, 1, 5, 9, 2, 6]

and we want its elements to be reordered in non-decreasing order - i.e. if one element is placed earlier (to the
left) than the other - we can be sure the first element is either less or equal to second.

Mathematically speaking, for any indexes `i` and `j` if `i < j` then `a[i] <= a[j]`.

**Bubble Sort** is one of the simplest methods to perform such reordering. We will describe it in even simpler way than
usually:

1. Take a `pass` through array, examining all pairs of adjacent elements (`N-1` pairs for array of `N` elements).
2. If for any pair with indexes `i` and `i+1` the condition `a[i] <= a[i+1]` does not hold, `swap` these two elements.
3. Repeat such passes through array until the new pass will do no swaps at all.

It is obvious, that if the pass do not perform any swaps, the array is already sorted and future passes could not
change anything.

To **swap** elements with indexes `i` and `j` there are few variants. For example temporary variable `t` could be used:

    t = a[i]
	a[i] = a[j]
	a[j] = t

###Problem Statement

We are going to implement the described version of Bubble-Sort. To test it we will check the amount of passes and amount
of swaps made before the given array becomes ordered.

**Input data** will contain array size in first line and array itself in the second
(integer values separated with spaces).  
**Answer** should contain two values - number of passes perfromed and total number of swaps made. For example:

    input data:
	8
	3 1 4 1 5 9 2 6
	
	answer:
	5 8

We may note that number of swaps is roughly proportional to `N^2` where `N` is array size (average is
about `N^2 / 4`) so that time which algorithm takes grows significantly faster than the amount of data (that is why
such sorting is rarely used for bigger arrays).

*Additional info can be found in the topic on [sorting algorithms comparison](../wiki/sorting-algorithms-comparison)*
