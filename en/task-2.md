<div class="centered">
<img alt="demo of summing an array" src="http://s5.postimg.org/ixq2y0nnb/sum_in_loop.gif"/>
</div>

Now our goal is to learn the **loops** - i.e. repeated actions.
Let us find the sum of several numbers (more than two). It will be useful to do this in a loop.
As shown in the picture above - you can create variable `sum` and add every value from the list to it.
Perhaps ["for" loop](http://en.wikipedia.org/wiki/For_loop) will suit nicely since the amount of numbers is known beforehand.

If you have troubles, try [Sums In Loop](./sums-in-loop) first - it is, probably, easier.

**Input data** has the following format:

- first line contains `N` - amount of values to sum;
- second line contains `N` values themselves.

**Answer** should contain a single value - the sum of `N` values.

Example:

	input data:
	8
	10 20 30 40 5 6 7 8
	
	answer:
	126

**Note** since there are several dozens of numbers, you should not copy them manually to your program.
Instead make your program reading them from standard input (where you can copy them all at once). Note that if you
run code at our server, the data are automatically copied to standard input for convenience.