Supposing you already read the story about [Shannon-Fano Coding](./shannon-fano-coding) (and even probably solved the
exercise) let us now learn the sequel of it.

One of the authors of that algorithm, **Robert Shannon** proposed the problem about searching for optimal
variable-length code to his student [David Huffman](http://en.wikipedia.org/wiki/David_A._Huffman) who at last came
upon brilliant idea - to build the code-tree in "reverse" order - i.e. not by splitting the array (as in case of
Shannon-Fano variant) but by joining elements into nodes.

Though the algorithm (as any based on character frequency) is not universally suitable, it is anyway often used.
For example while browsing internet you see a lot of images in either `JPEG` or `PNG` format. Both of these formats
use Huffman at some stage of processing.

###Algorithm

Let us start with the example. Given the sample text `DAVIDAHUFFMAN` let us at first count the usage of letters and
sort them for convenience according to counts:

    char	count
	A		3
	D		2
	F		2
	H		1
	I		1
	M		1
	N		1
	U		1
	V		1

Now let us at each step take two entries with the smallest counts and join them into a new element - supposing it to
be a tree node, so that one entry goes to the right hand and another to the left.

At first we will join `U` and `V`. Total count for new node would be `1+1=2` so we reinsert the node into the array:

	A=3  D=2  F=2  (U,V)=2  H=1  I=1  M=1  N=1

Two more steps and we join `M` with `N` and `H` with `I`:

	A=3  D=2  F=2  (U,V)=2  (M,N)=2  (H,I)=2

The following step requires us to join pairs of letters `M,N` with `H,I` - their total count will be `4`:

	((M,N),(H,I))=4  A=3  D=2  F=2  (U,V)=2

Then we couple the single letter `F` with the pair `U,V`:

	((M,N),(H,I))=4  (F,(U,V))=4  A=3  D=2

The following steps are similar - we join rightmost nodes and insert them again according to their total count:

	(A,D)=5  ((M,N),(H,I))=4  (F,(U,V))=4			- A and D
	
	(((M,N),(H,I)),(F,(U,V)))=8  (A,D)=5			- quadruple M-N-H-I with triple F-U-V
	
	((((M,N),(H,I)),(F,(U,V))),(A,D))=13			- the whole tree is built

You probably noticed that when we join the two rightmost nodes we still preserv their order so that most frequent
goes to the left branch and least frequent to the right.

Our resulting record resembles one used in [Tree Builder](./tree-builder) exercise, so let us plot the tree:

                                 |
                       +---------+--------+
                       |                  |
              +--------+-------+      +---+---+
              |                |      |       |
        +-----+-----+      +---+---+  A       D
        |           |      |       |
	+---+---+   +---+---+  F   +---+---+
	|       |   |       |      |       |
	M       N   H       I      U       V

As earlier, bit-sequence for each letter is defined by the way from the root of the tree. For example, let us now use
`1` for left branches and `0` for right ones:

    char	code
	A		01
	D		00
	F		101
	M		1111
	N		1110
	H		1101
	I		1100
	U		1001
	V		1000

The total message length will be `40` bits for `13` characters, i.e. about `3` bits per character. To calculate this
we simply write down the letters, length of their codes and counts:

    char	count	length
	A		  3       2
	D		  2       2
	F		  2       3
	H		  1       4
	I		  1       4
	M		  1       4
	N		  1       4
	U		  1       4
	V		  1       4

then multiply counts by lengths and at last summarize them all:

    3*2 + 2*2 + 2*3 + 1*4 + 1*4 + 1*4 + 1*4 + 1*4 + 1*4 = 40

It was proved by Huffman that the code constructed by this algorithm is optimal - i.e. no any code using whole
amount of bits for each character allow to compress text into smaller resulting bit-string if it relies only upon the
frequencies of the characters.

*Better results could still be achieved with **Arithmetic Coding** which in its core allows to use fractional amounts
of bits.*

###Problem Statement

Given a fragment of text you will be asked to find the compression ratio provided by Huffman's algorithm:

                 original size
    ratio = -----------------------
	            compressed size

I.e. in case with `DAVIDAHUFFMAN` original size is `13*8=104` bits while compressed size is only `40` bits, so the
compression ratio is `2.6`. We assume that original text was encoded using `8` bits per character.

*With real 

**Input data** will contain a sample of text, consisting of letters, punctuation marks, spaces and probably digits.  
**Answer** should contain a single real value - the compression ratio (with `1e-6` precision or better).

Example:

    input data:
	DAVIDAHUFFMAN
	
	answer:
	2.6

**Note** that real implementation of the algorithm also needs to store the code-table or counts-table in the resulting
file - this slightly reduces the compression ratio especially if the original size is comparatively small.

**Homework:** would you like to compare compression ratio for Huffman algorithm with one of Shannon-Fano?