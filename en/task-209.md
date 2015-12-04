Recently we learned about [Suffix Array](./suffix-array) - convenient data structure for building search
index over the text. However for texts of significant length we, probably, could not just extract
all suffixes and sort them in naive way. This may take up to `O(n^2)` of memory and about `O(n^2 * log(n))`
of time if comparing two substrings takes `O(n)` [as wikipedia says](https://en.wikipedia.org/wiki/Suffix_array#Construction_Algorithms)
discussing efficiency of different algorithms.

So let us try building suffix array over the larger text. Good books, like **The Holy Bible** or
**Lord of the Rings** contains usually few hundreds thousand words, so let us create similar data set.

1. We will load words from our favorite [**words.txt**](http://www.codeabbey.com/data/words.txt) file into single list.
2. Then we set up [Linear Congruential Generator](./linear-congruential-generator) with the usual
	parameters (`A = 445`, `C = 700001`, `M = 2097152`).
3. And we'll generate `N` random values starting with given seed - then turning these values into
	indices for the word list (taking modulo by the size of the list if necessary).
4. Let us concatenate these extracted words with spaces into a single string (thus representing a large book),
	and then build suffix array for such a string.
5. To check the answer we'll use [array checksum](./array-checksum) - just as in that old problem.

**Input data** will contain two integers - amount of words `N` to create a "book", and the initial
value `X0` for our random generator.  
**Answer** should contain checksum of the resultant suffix array.

<div class="attention">
<span class="strong">Time limit - 90 seconds</span> - please do not forget to reload the page to
generate new data and reset timer before copying these data to your program.
</div><br/>


Example:

	input data:
	9 13
	
	answer:
	7897656

Explanation:

With seed of 13 we generate 9 random values:

	705786 201971 399560 246281 1243142 250063 828980 497349 1819346

Corresponding to words from list with the following indices:

	1808 9977 15572 54287 27180 58069 61004 49363 27402

e.g. forming the following string:

    anagrams clumsy dingy storks hurt townspeople vaguest scrimshawing icicle

and then the suffix array is calculated as following:

	[73, 8, 15, 28, 66, 53, 21, 33, 45, 2, 47, 5, 0, 61, 68, 70, 9, 55, 16, 72, 44, 40, 50,
		65, 3, 48, 19, 60, 29, 67, 69, 57, 63, 17, 26, 71, 43, 10, 6, 58, 12, 1, 64, 18, 37,
		41, 24, 35, 39, 42, 4, 56, 25, 31, 7, 27, 54, 59, 38, 51, 22, 13, 52, 32, 23, 34, 49,
		11, 30, 46, 62, 36, 14, 20]

**Note** that the empty string is also included into suffix array and takes the very first place
(for string `S` of the length `L` it is `substring(S, start = L, length = 0)`).
