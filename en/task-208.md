Do you remember Brother Geeglo? After successfully [opening the door of ancient wine cellar](./lexicographic-permutations)
he became famous for
having mystery skills of breaking ciphers etc. Just yesterday he was called from the Government House, by prime
minister Sclerozzio. This decent man had a misfortune of forgetting the codeword for the lock of
his secret safe.

Mr Sclerozzio related that:

- the codeword was made up of several letters taken from his wife's name;
- he remembers word `S` which is similar to codeword;
- this similar word may have up to `D` errors comparing to codeword (e.g. wrong letters at some positions).

For example, if the alphabet contains letters `E L I Z A`, and Sclerozzio remembers the word as `ZLAIAZAIA`, then
the codeword could be `ELAIAZAIL` (2 letters different), but not `ELIZAZAIA` (3 letters different).

Let us help brother Geeglo to **generate all possible codewords in alphabetical order**,
so he can brute-force the lock as fast as possible.

Such a set is called the `neighborhood` of the given string. The string itself is usually included into its
neighborhood (i.e. perhaps `S` is the proper codeword and Sclerozzio just failed to set it properly).
This task can be solved by several different algorithms - some of them non-effective and dull, but still working
with small values of `D`.

_I came upon this problem in the [beginner's course of Bioinformatics](https://www.coursera.org/course/hiddenmessages)
(by Coursera and University of California, San Diego). They use it when it is necessary to find some frequent
patterns in DNA, probably affected by mutations._

###Problem Statement

**Input data** contains the letters of alphabet in the first line.  
Second line contains `S` - the word recollected by Sclerozzio.  
Third line contains value of `D`.  
**Answer** should contain all words with no more than `D` differences from `S`.

Example:

	input data:
	E L I Z A
	ZLA
	2
	
	answer:
	AAA AEA AIA ALA ALE ALI ALL ALZ AZA EAA EEA EIA ELA ELE ELI ELL ELZ EZA IAA IEA IIA ILA
	ILE ILI ILL ILZ IZA LAA LEA LIA LLA LLE LLI LLL LLZ LZA ZAA ZAE ZAI ZAL ZAZ ZEA ZEE ZEI
	ZEL ZEZ ZIA ZIE ZII ZIL ZIZ ZLA ZLE ZLI ZLL ZLZ ZZA ZZE ZZI ZZL ZZZ

Note that answer is split to several lines here just for clarity.
