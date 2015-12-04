<div class="text-center">
	<img src="http://s5.postimg.org/lzbef0q0n/suffix_array.png" alt="wizard with books"/>
</div>

There is the Library of Secret Knowledge in the Abbey. It consists of few hundreds books and old
brother Bartholomew - the wise librarian.

The main problem with the Secret Knowledge is that you never know where to search for specific topic.
For example if I want to read about `radiophotoplethysmograph` - what book should I pick and which
page to open? Brother Bartholomew can help with this often, but even he do not know all thes books
by heart.

That is why he wants to have an electronic version of the Library. He can manage to scan and recognize
old manuscripts, and save them to files. However there is still some problem: the total volume of
the data is about `1 Gigabyte`. If one person wants to search some word in it by simple scan, it will take about
`30 seconds`. However if the Library is made public and have many visitors from internet, it is too much.
If we have `300` users each of them making `10` search requests - the server will work for whole day.

But as the data to be searched through are the same for every request, can we prepare them in some
manner to speed up these requests? Yes, we can. We want to create an `index` of some sort.

**Suffix Array** is one of popular types of such indexes. We are going to see how it works and then
try an exercise about creating one. The core idea of `suffix`-based data structures is like following:

- represent the whole data as a single text string (e.g. concatenate all electronic books into one file);
- the `suffix` is a substring starting at any position and running to the end of this text;
- so for string of `N` characters we have `N` different suffixes - let us extract them to some set or list;
- now we create some sorted structure of these suffixes - e.g. sorted array or binary tree;
- and we are ready to process requests - if we have some search word, we can find all suffixes
	which start with this word (i.e. have it as a prefix) in no longer than `O(log(N))` time - for
	gigabyte it is about only about `30` comparison operations - i.e. few microseconds;
- by the suffixes found we may know to which position of original text they belong (by their length,
	for example) - and so we'll find the corresponding book and the page.

The only trouble is how to store this set of suffixes efficiently. The suffix array is probably the
most compact way. Let us see how it looks like.

###Suffix Array by Example

Suppose we have the long text string like `INTERPRETING` (it is not gigabyte, but sufficient for our
example). Let us write every possible suffix in the alphabetically sorted list - and their starting
positions in the string:

	ERPRETING		-	3
	ETING			-	7
	G				-	11
	ING				-	9
	INTERPRETING	-	0
	NG				-	10
	NTERPRETING		-	1
	PRETING			-	5
	RETING			-	6
	RPRETING		-	4
	TERPRETING		-	2
	TING			-	8

This column on the right - it is just **suffix array**. Do you see how it is used in the search?

Suppose we want to find the word `SUB`. We use **binary search** - let us peek into the middle of array (say at position `5`,
counting from `0`) and see prefix `NG` here. It is alphabetically smaller than our word. So we now
peek at the middle of the second half of array, say at position `8`. Here is prefix `RE...` - it is
alphabetically less than our word so we should look between the positions `8` and the end.
We'll find `TE...` at position `10` and then we need to search between `8` and `10`. So we will
use about `4` or `5` attempts to discover that the search word is not found anywhere.

We used the example of non-existing word intentionally since it always gives the longest search path.
Anyway the path is about `log(N)` attempts (with binary logarithm).

###Problem Statement

You are given some piece of text and your goal is to print out the suffix array for it. We do not
discuss the algorithms for building suffix arrays - they could be very fast and very complicated -
but you can safely use `naive` approach for the sample text will be just about `200` characters long.
We want to learn the concept right now, not specific algorithm.

**Input data** will contain a single line of text (capital latin letters and spaces).  
**Answer** should give a suffix array for this line - list of integers.

Example:

	input data:
	INTERPRETING CREATES RATES
	
	answer:
	12 20 22 16 13 15 3 24 18 7 11 9 0 10 1 5 21 14 6 4 25 19 2 23 17 8
