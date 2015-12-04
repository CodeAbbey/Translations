Excercise on [Luhn Algorithm](./luhn-algorithm) provided the simple example error detection code. We even used it as an
**error correction** code though in practice it is not common.

Now we are going to get acquainted with another popular algorithm - **Hamming Coding**. It is applied to a sequence of bits
and allows to correct any single bit error or to use it as error detection for up to two-bit errors.

This algorithm was created by [Richard Hamming](http://en.wikipedia.org/wiki/Richard_Hamming) to correct mistakes of device
used for reading the program from **punched cards** - and nowadays it is widely used in computer RAM memory modules. The
algorithm suits this task quite well because errors in memory modules are very rare and independent, so the error in more
than one bit of the same memory word is as unlikely as winning Jack-Pot without buying lottery ticket.

###Algorithm Description

The method looks rather whimsical at first glance so we'll try to demonstrate it with example.

Suppose we have a string of bits (say of length `12`, though any length will do):

    1 0 0 1 1 0 1 1 1 0 0 1

Let us rewrite it inserting **empty spaces** at positions with numbers equaling to powers of `2` (starting count from `1`,
instead of `0`, which is somewhat unusual):

    _ _ 1 _ 0 0 1 _ 1 0 1 1 1 0 0 _ 1

You see, we inserted `5` blank spaces which will be used for **parity bits** - at positions `1`, `2`, `4`, `8`, `16`.

To calculate each of these bits we `XOR` some others. Namely, to calculate parity bit at position `i` we should xor all
bits at positions the number of which (also `1`-based) yields non-zero when `and`-ed with `i`.  
I.e. for parity bit at position `1` we should xor bits at positions `1`, `3`, `5`, `7`...  
For parity bit at position `2` we should xor bits at positions `2`, `3`, `6`, `7`, `10`...

Some parity bits themselves may need to be xored - so we should initially regard them as containing `0`-s.

The picture below illustrates this process.
	
	_ _ 1 _ 0 0 1 _ 1 0 1 1 1 0 0 _ 1
	
	X   X   X   X   X   X   X   X   X	- these bits are XOR-ed to get 1-st parity bit
	  X X     X X     X X     X X       - these bits are XOR-ed to get 2-st parity bit
	      X X X X         X X X X       - these bits are XOR-ed to get 4-th parity bit
		          X X X X X X X X       - these bits are XOR-ed to get 8-th parity bit
				                  X X   - these bits are XOR-ed to get 16-th parity bit

    0 1   1       0               1     - here are these parity bits
    ---------------------------------	
	0 1 1 1 0 0 1 0 1 0 1 1 1 0 0 1 1   - and this is the output bit string

You may note two interesting facts:

- that each of bits participates in calculation of different set of parity bits;
- XOR-sums calculated above with the updated values of parity bits will always be `0`.

This leads to interesting property. If any bit have changed its value by error (from `0` to `1` or vice versa) - it will
therefore change several of these xor-sums to `1`. And in each case the pattern in which sums were changed will be unique.

For example, suppose that the bit `#9` was changed from `1` to `0`. It will obviously change the `1-st` and `4-th`
checksum (xor-sum) to `1` so that the total row of checksums will look like

    5th 4th 3rd 2nd 1st
	
	 0   1   0   0   1

Wonderful! This is binary representation of the decimal value `9` - exaclty the position where error occured. So we simply
need to invert this bit.

If there were no error, then value `0` is produced by these checksums - that is why algorithm uses `1`-based indexing.

It does not matter whether error have changed one of data bits or some parity bit - any of them may be fixed.

_If the explanations still seem vague to you please refer to
[wikipedia article](http://en.wikipedia.org/wiki/Hamming_code) for more info._

---

###Problem statement

The exercise consists of two parts.

In the first part you are to perform Hamming encoding on several bit strings (i.e. to add parity bits to them as described
above).

The second part on contrary gives you a handful of bit strings with Hamming's parity bits - and each of the strings
may contain error in a single bit. You are to decode them.

**Input data** will contain the following sections:

- the value `N1` - quantity of strings for encoding;
- then `N1` lines will follow with these bit strings;
- the value `N2` - quantity of bit strings for decoding;
- and at last `N2` lines with these strings for decoding.

**Answer** should contain processed bit strings for all cases.

Example:

	input data:
	3
	111101
	01011111
	01110110
	6
	110111111
	010100111
	001100011
	0001111000
	0110011
	1001001101
	
	answer:
    1011111101 010110101111 100111100110 01111 00011 10101 011100 1011 000101
