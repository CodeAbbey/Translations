Nowadays many applications perform spell-checking as you type in text. Among first programs to implement this feature
was **Microsoft Word** - you know, you type the misspelled word and it is marked with red wavy line below.

You also know that usually such spell-checking not only checks the word in question by some internal vocabulary, but
also suggests some substitutions. For example if you enter `crain` you are proposed to change it to `brain`, `train` or
`chain`.

How these substitutions are chosen? One of the basic and popular solution is to run through vocabulary and calculate
the Levenshtein Distance between the misspelled word and each of
dictionary words. Words which give minimal distance are, probably, the best substitutions.

**What is the Levenshtein Distance?**

Shortly speaking it is the **diference** between two strings. Levenshtein distance counts `1` point of penalty for each
of three mismatch kind:

- the letter is present in the first string but absent in the second (like `plain` and `plan`);
- the letter is absent in the first string but present in the second (like `tree` and `three`);
- the letter is different in the same position of two words (like `woman` and `women`).

As an example, let us see what is the distance between `hate` and `shot`:

    hate -> hat      (one letter removed)
	hat  -> hot      (one letter substituted)
	hot  -> shot     (one letter inserted)

So the distance is `3`.

**Your task** now is simply to calculate the Levenshtein Distance between two strings. There are different algorithms,
of which most popular uses dynamic programming with a table **M by N** (however it could be reduced to only two lines,
previous and current, reassigned after each current line is completed). You can read more
in the wikipedia article on [Levenshtein Distance](http://en.wikipedia.org/wiki/Levenshtein_distance) or get info
from many other sources.

**Input data** will contain the number of test-cases in the first line.  
Next lines will contain 2 "words" each - words will contain of capital latin letters only.  
**Answer** should contain the distances for each pair of words, separated by spaces.

Example:

    input data:
	5
	PLAIN PLAN
	TREE THREE
	WOMAN WOMEN
	KITTEN SITTING
	YPOEHOHRIWUBXMNHZF YCPOEHORIDUBXNHZF
	
	answer:
	1 1 1 3 4

*Note: this algorithm works good for languages where words are pronounced similarly to how they are spelled, like
Italian, Russian, German etc. However, it is not very good for English, where `women` is pronounced like `weeman` etc.,
so the English have more special and complicated algorithms, like [Soundex](http://en.wikipedia.org/wiki/Soundex).*