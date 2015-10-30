The part of LZ77 compression algorithm is about searching of a substring in the text
directly preceeding it.

Let us see an example with the following text:

	in the town where i was born lived a man who sailed to sea
	and he told us of his life in a land of submarines

starting from the words `and he told` we can discover the following repeating fragments:

- `"an"` was encountered before in the word `man`;
- `"d "` (letter with the following space) was encountered inside words `sailed to`;
- `"he to"` was encountered within `the town`;
- `"l"` (just a single letter) is found inside `sailed`;
- `"d "` (again the letter with space) is something we have already seen...

This exercise asks you to find **the longest** of preceeding matches for several positions in the text.
**Note** that while for real compression algorithm it is crucial to implement this efficiently,
for the given exercise it is not needed - it is only important to get the idea of encoding with back-references.

###Details

Preceeding match should be sought for only within the block of preceeding `4096` bytes and the match of no more than
`15` bytes is required. This will allow us to encode the position of the match with `12-bit` value and the length of
the match with `4-bit` value - i.e. only two bytes in total.

Position (or rather **offset**) of the match should be calculated relatively backward to current position,
so that the first preceeding symbol has the index `0`, the next `1` and so on up to `4095` (i.e. it is the difference
of positions of the current substring and its previous match decreased by `1`).

Returning to our example above:

	string   off-len
	
	an        20-2
	d_        10-2
    he to     58-5
    l         19-1
    d_         7-2
    u          0-0

In the last case the length `0` shows that even substring of the length `0` could not be found.

**If more than one prefix of the same length could be found, please choose the smallest offset.**

As a source text to fetch input data from please use the sample data file:

[Click with right button and choose 'save as' to download file **doyle.txt**](http://www.codeabbey.com/data/doyle.txt)

It is not large so it is recommended to store it in a single long byte array in your program to handle easily.

###Input/Output specification

**Input data** have the number of testcases `N` in the first line.  
Second line contains exactly such amount of positions `Pi` for `i=1..N` for which the search should be done.  
**Answer** to each case should be `2`-byte hexadecimal with its lowest `12` bits (or `3` digits) holding the offset
and the highest `4` bits (one digit) storing the length (so that offset `20` and length `2` are encoded as `2014`,
while `58` and `5` as `503A`).

Example (with real `doyle.txt` file):

	input data
	13
	22255 22947 36587 9700 31780 21915 4676 25611 34708 13155 7630 46121 20855
	
	10D7 59A4 3167 3007 301E 6AE7 3334 4721 3C77 7AD1 7F21 214A 3B04

Here the substring from position `22255` reads `kable` and no better match could be found before rather than
single letter `k` at position `22039`.

The substring from position `22947` is `led to listen` and match of `5` letters is found at position `20478`
inside the phrase `disentang[led t]he most`.

You may trace other matches manually to get the idea better.

<script>
noServerRun = true;
</script>