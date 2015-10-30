In the problem on [Variable Length Code](./variable-length-code) we used some predefined code-table without explaining
where it comes from.

Now it is the time to learn how such a table could be created.

Of course we do not want some random distribution of variable-length codes. Instead it is interesting to create the
table in which more frequent bytes are encoded with shorter bit sequences.

Very simple approach was proposed by the "Father of Information Theory"
[Claude Shannon](http://en.wikipedia.org/wiki/Claude_Shannon)
and, probably bit earlier, another influential scientist in the same field
[Robert Fano](http://en.wikipedia.org/wiki/Robert_Fano).

It is not optimal encoding, but nevertheless it is sometimes used (because it is close to optimal anyway). For example
one of the algorithms uzed by **ZIP** archiver (and some its derivatives) utilizes Shannon-Fano coding. Anyway later
you may write the program for more popular [Huffman Coding](./huffman-coding).

###Algorithm

Let us see how it works. For example, let the source text consist of the single word `ABRACADABRA`. Start with writing
down the count of different characters (or bytes) used:

    char    byte	count
	A		65		5
	B		66		2
	C		67		1
	D		68		1
	R		82		2

Now let us sort them in order of decreasing the counts:

    A	B	R	C	D
	5	2	2	1	1

And split the resulting array into two parts so that total counts in each part are as close to each other, as possible:

    A	|	B	R	C	D
	5	|	2	2	1	1

Here total on the left is `5` and total on the right is `6`.

Now we say that all characters in the left part should start with a bit `0` while all in the right part should start
with a bit `1`.

Since in the left part there remains only one character at all, it will therefore be encoded with a single `0`. But
the right part contains more characters and we should repeat the operation of splitting it into parts:

    B	|	R	C	D
	2	|	2	1	1

Here the left part has total of `2` and right of `4` - obviously not quite equal, but we could not do better with a
sorted array. So the letters in the left part will have the second bit `0` and ones in the right part will have the
second bit `1`.

We proceed with splitting the right part twice times more so at last we can construct the [Binary Tree](./tree-builder)
looking like this:

              |
	 +---0----+----1----+
	 |                  |
	 A          +---0---+---1---+
	            |               |
				B       +---0---+---1---+
				        |               |
						R         +--0--+--1--+
						          |           |
								  C           D

And the corresponding code-table is built by this tree simply traversing its branches and writing down the bits:

    char	byte	code
	A		65		0
	B		66		10
	R		82		110
	C		67		1110
	D		68		1111

*Note that tree for word `ABRACADABRA` has all left parts consisting of a single letter, but it is only due to fact of
quite unbalanced letter distribution. Another thing is that in the previous problem of "Variable Length Code" we
used `1` for left branches and `0` for right, but this choice does not make difference.*

###Breaking Ties

There are two things which may lead to different code tables being produced for the same source.

Let us agree that if splitting of some sub-array could be done in two ways giving equally close results, like in case
of letters `B-R-C-D` which could be split either as shown above or like this:

    B	R	|	C	D
	2	2	|	1	1

With the totals `4` and `2` instead of `2` and `4` - in such cases we will choose the "leftmost" split of two.

Also let us agree that in the initial sorting if two letters have the same count (like `B` and `R` or `C` and `D`)
they will take the place in our array in their lexical order (i.e. by increasing of their ASCII codes).

###Problem Statement

You will be given a fragment of text consisting of letters, spaces, punctuations and probably digits.
You are to create the code-table by the rules above.

**Input data** will contain the text in a single line.  
**Answer** should contain the pairs of ASCII-values and corresponding bit-strings of Shannon-Fano coding. Please
output ASCII as decimals while bit-strings using letters `O` and `I` instead of digits `0` and `1` to help us
determine possible mistakes easier. Also output the results **in the same order** as the letters were sorted during
the algorithm.

Example:

	input data:
	ABRACADABRA
	
	answer:
	65 O 66 IO 82 IIO 67 IIIO 68 IIII

**Homework:** since now you can construct proper Shannon-Fano code table for any arbitrary file (either text or binary)
would you like to try to write a **Shannon-Fano Compressor** which creates such a table and then writes the file using
it. Of course resulting file also should contain either the code-table or initial counts of bytes so that decompressor
could use the same codes or at least reconstruct them.