Hope you've already solved [Variable Length Code](./variable-length-code) problem and have written a program to compress
the text. Now our goal is to decompress it back.

Use the same code-table to decrypt the result of compression of some message. The most effective way is to represent
the table as a binary tree with letters in the leaves and use bits of the stream to traverse this tree from the
root.

To make the exercise look bit more different we use another way of representing compressed stream. It is split into
chunks of `5` bits (instead of `8`) and then these chunks are converted to digits of numeral system with base `32`, i.e.
one of the characters:

    0123456789ABCDEFGHIJKLMNOPQRSTUV

For example the compressed sequence:

	0SA14NH2CG2K8GH1GOD604

represents the following bit stream:

	00000 11100 01010 00001 00100 10111 10001 00010 01100 10000 00010 10100 01000 10000 10001 00001
	10000 11000 01101 00110 00000 00100

And at the end it is just encoding of the same phrase `world of !programming` (which we have seen already).

Note that the compressed stream could be padded with trailing zeroes, which anyway do not correspond to any character
in the table and so could be unambiguously removed.

**Input data** contain a single string - very long `32`-based number, representing the compressed data.  
**Answer** should contain the decoded text.

Example:

    input data:
	44TGUUM8OAIBI4Q01JI0M462KALCA0

	answer:
	!i am a stupid !text !compressor

---

###Optional Exercise

**We encourage you** to modify your solutions for both these exercises to create the tools for encoding and decoding
text files (so that compressed data are written as real bytes). Since usual files contain more characters you'll need
to invent some additional encoding scheme. As a simple idea you can ignore letter case (convert all to lowercase)
and use exclamation mark with some letter to represent punctuation and special characters, like this:

    !n - new line
	!d - dot
	!c - comma
	!e - exclamation mark
	!t - dash
	!q - question mark
	!a - quote
	
So the pre-conversion phase will go like:

    "Was it a cat I saw?" - asked Alice, as
	she ran further.
	
	!awas it a cat i saw!q!a !t asked alice!c as!nshe ran further!d

Then try your tools with some long text file (some book downloaded from [Project Gutenberg](http://gutenberg.org) and
compare the size of compressed and uncompressed files.

*By the way, for the exercise you perhaps have used very inefficient algorithms to work with bits,
but for processing large files you may want to optimize it to work faster.*