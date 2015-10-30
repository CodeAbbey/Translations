Among the three simple sorting algorithms with quadratic time complexity, the Insertion Sort have sove special
qualities, of which probably few most important are:

- it requires smaller amount of comparisons so it is the fastest when comparing elements is slower than moving them
	(sorting strings for example);
- "online" or "adaptive" sorting is possible with it - i.e. adding new elements to already ordered list (and maintaining
	it sorted);
- this method could be quite easily applied to linked list instead of array.

Let's see how it works.

###Algorithm

Suppose we have some sub-array (or list) already sorted. How hard would it be to add one more element to it, keeping
data still ordered?

We should search through initial sub-array and find a place where new element should be inserted. To insert it we,
of course, need to shift all elements which are larger. See an example:

    1 3 5 6 8   - initial array
	4           - another element to add
	
Searching through array we see that `4` should be inserted where `5` currently is. Let us shift all elements starting
from `5`:

    1 3 _ 5 6 8 - we shift the upper part of array
	1 3 4 5 6 8 - and insert new element to empty cell

Now it is easy to create a method for sorting the whole array!

Starting with unordered list of elements, like this:

	[3, 1, 2, 5]

Let the very first element be our "initial ordered sub-array". Obviously array of a single element is always ordered :)

    [3], 1, 2, 5

Now at each step we'll be inserting into the "current sub-array" one element immediately following it. On the first
step we are going to insert `1`, we can do it as following:

- copy the element to be inserted into temporary variable `T`;
- find the place to insert it inside the current sub-array (now it should go before `3`);
- shift the part of sub-array, starting from this place - the sub-array is extended and the value which we are
    inserting is overwritten, but we have saved it inside temporary variable;
- copy the value from `T` to the proper place in updated sub-array.

So the process will go like this:

    [3], 1, 2, 5            T = 1, it should be inserted before 3
	[3, 3], 2, 5            part of array starting from 3 is shifted, 1 is overwritten
	[1, 3], 2, 5			1 is restored from T to the proper place
	
	[1, 3], 2, 5			T = 2, it should be inserted before 3
	[1, 3, 3], 5            part of array starting from 3 is shifted, 2 is overwritten
	[1, 2, 3], 5            2 is inserted from T to sub-array
	
	[1, 2, 3], 5            T = 5, it should be inserted... after all other elements, nice!
	[1, 2, 3, 5]            nothing to shift! we just extend sub-array to have 5 in it.

###Variants

Comparing to [Selection Sort](./selection-sort) we can see that more moves (copying) of array elements is performed,
but probably less comparisons. So benefit of the Insertion Sort is for objects which are handled by references (as in
most contemporary languages) but for which comparison takes significant time.

Since we are always searching through already sorted sub-array, we can use a kind of [Binary Search](./binary-search)
here, which will allow to decrease the amount of comparisons dramatically.

We can also perform "shift" in lazy way - simply making swaps of currently inserted element with all preceding ones
until it is less than they. It makes the algorithm resemble bubble-sort and decreases its efficiency, but greatly
simplifies implementation.

###Problem statement

You are given an array of values to sort. Implement the described algorithm and at each pass print out how many
elements of the array were shifted.

**Input data** will contain `N` - the size of array - in the first line.
Next line will contain the array itself (all elements will be different).  
**Answer** should contain `N-1` values showing how much elements are shifted at each pass.

Example:

    input data:
	4
	3 1 2 5
	
	answer:
	1 1 0