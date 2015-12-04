You probably know about [Look and Say](http://en.wikipedia.org/wiki/Look-and-say_sequence) sequence - one which is
constructed by splitting the current value into same-digit sequences and then writing down how many times each digit is
repeated. It starts like this:

    1		- sequence of 1 digit 1  =>  11
	11		- seqeunce of 2 digits 1  => 21
	21		- sequence of 1 digit 2 and another of 1 digit 1  =>  1211
	1211    - 1 digit 1, 1 digit 2, 2 digits 1  => 111221
	111221  - 3 digits 1, 2 digits 2 and 1 digit 1  =>  312211

And so on. You may see this sequence increase without limit for almost any starting value.

Since we are programmers, let us describe binary variation of this sequence. Let us start with some binary value:

	100011001

Splitting it into sequences give us

	1 digit 1, 11 digits 0, 10 digits 1, 10 digits 0, 1 digit 1

Note that we write counters as binary also, of course. Also there are two obvious facts:

- any binary value starts with `1`, so first sequence always consists of `1`-s;
- since there are only `2` possible digits, sequences of `0` and `1` are following each other.

This gives us significant improvement: we only need to write lengths of sequences, but not the digits themselves.
E.g. the value above could be written as lengths of sequences:

    1 11 10 10 1  => 11110101

This improvement changes the behavior of sequence dramatically. Instead of growing with each step it steadily decreases
in length until reaching loop of `11`, `10`, `11`, `10`. Another loop of single value `1` could not be reached from any
starting value except `1` itself.

Note that we can come to `10` only from `11` (i.e. it have a single parent), while there are two possible "parents"
for `11` (namely `10` and `111`).

###Problem Statement

**Input data** will give you a random binary value.  
**Answer** should tell how may steps it take to reach value `10` and how many other sequences produce the given one
on the first step (i.e. how many "parents" it have).

Example:

    input data:
	1110100011000011001001001111011110000100111000101110111100
    
	answer:
	23 536870912
