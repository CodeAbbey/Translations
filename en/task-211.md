_Back in 1997 I was taught to use file archivers. I grew curious - whether I can compress file with ZIP, then
compress this archive with RAR, then pack the result with ARJ, and pass what I get to HA - etc. until the data
are compressed to the single byte. So that I can remember this byte and erase the file... Funny idea?_

You may remember the exercise about [Variable Length Code](./variable-length-code) and related problems (e.g.
algorithms of Shannon-Fano and Huffman). All of them give us idea that the more redundancy data have - the better it
could be compressed.

Claude Shannon besides other inventions suggested the metric which directly shows how well the information could be
packed. This metric is called [Entropy](https://en.wikipedia.org/wiki/Entropy_(information_theory)) - sometimes also
"Shannon's Entropy". It can be interpreted as lower limit of bits per unit of data (e.g. per every byte of the file, or
character of the message) which could be achieved by ideal compression scheme.

The formula, if applied to the sequence of characters (or file of bytes) looks like:

	H = Sum(P(c) * -log2(P(c))
	
where `P(c)` is the frequency of the given char `c` in the data.

Let us see few examples to understand it better.

    AB

This message consists of only two characters, each of them is encountered once, so frequency is `0.5`.  
That gives `log2(0.5) = -1` and the total sum is `0.5 * 1 + 0.5 * 1 = 1` - i.e. we need `1` bit for each character.
Really, we can encode one of letters with `0` and another with `1`.

Now, another string with equal frequencies:

    TED_LIAR

The frequency will be `0.125`, giving `log2(0.125) = -3` and so the entropy is `3`. Really - to encode `8` different
characters we need exactly `3` bits.

But what if some characters are repeated?

    BOOK

Here `p(O) = 0.5` while `p(B) = p(K) = 0.25` and we have total sum:

    H = 0.25 * 2 + 0.5 * 1 + 0.25 * 2 = 1.5

Really! We can use variable length codes: `O` is `1`, while `B` is `00` and `K` is `01`. The whole message will need
`6` bits which gives `1.5` bits per letter average.

###Connect it to Reality

If we create entropy calculator for files, we'll see that for text file entropy is low (about `3`),
but after we compress it, say, with ZIP archiver - it reaches almost `8`. That is why compressed files are hard to
compress further.

The product of `length(text) * entropy(text)` gives idea of how much "real information" the text contains. (How does
it change after text is compressed?)

The important thing to note is that we can calculate frequency in more whimsical manner - for example, make it
dependent on previous character. This will lead to encoding scheme similar to [LZ77](./lz77-decompression) but the
entropy formula will still work. If we can get lower entropy with some complicated definition of frequency - then we
can create better compressing algorithm (but based on more complicated idea).

It looks surprising, but for some samples (like `IEEE`) entropy is less than `1`. Some encoding techniques really
allow to pack data using less than single bit per character! (for example - arithmetic encoding)

###Problem Statement

We are given several messages and the task is just to calculate entropy for each of them. Messages are composed of
small latin letters and spaces, so we may expect entropy could not be greater than `5` (as `5` bits are enough
for `32` different characters, while we have at most `27`). We'll see that real values for these messages are
usually between `3.0` and `4.0`.

**Input data** will give number of messages in the first line.  
Next lines contain messages themselves.  
**Output** should tell entropy for each of messages, as a floating-point value (with accuracy `1e-7` or better).

Example:

	input data:
	5
	team eats cheese
	president plays with zooophthalmology
	helena plays with pigeons
	government loves beer
	irina dreams of clothes
	
	answer:
	2.77439747035 3.98285666332 3.7034651896 3.363286924 3.7950885864
