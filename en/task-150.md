This is the first task to be solved with the help of regexps.

Your **Code** should contain one or more lines, each consisting of two parts separated with space:

- regular expression to be applied to input;
- substitution pattern.

These regular expressions and substitutions are applied to each line of the input in order. If the given regexp will
found the matching framgent inside the line, it will be substituted with the given pattern.

For example an input like this:

    aaaaa bbbb aaabb

Could be processed with the following solution:

    a+ X
	b+ Y

and the following result would be produced:

	X Y XY

If input consists of several lines, they will be processed independently (though results are glued together into
a single line with spaces).

Regexp format used here is one of [PHP Regexps](http://php.net/manual/en/reference.pcre.pattern.syntax.php) - it is
very close to Perl-style regexps, I hope.

###Problem statement

You are given a set of integers in `decimal`, `octal`, `hex` and `binary` format as they are used in several
programming languages (derivatives from `C` and `Assemblies`):

- value consisting of digits `0-7` and starting with `0` is octal;
- value consisting of digits `0-9ABCDEF` and starting with `0x` is hexadecimal;
- hexadecimal could be instead suffixed by `h` but then it should not start with letter;
- binary could be written as `0b1000101` or `1000101b`;
- values consisting only of digits `0-9` are considered decimals (but not ones starting with zero -
	they should be regarded as octals and coul only	contain digits `0-7`).

And your goal is to recognize these formats. Note that all letters (in hexadecimal values and in prefixes / suffixes)
should be treated **case-insensitively**!

**Input data** will contain several "integers", each on separate line.  
**Answer** should contain replacements for them - `dec` for decimals, `oct` for octals, `bin` for binaries
and `hex` for hexadecimals. Strings which could not be recognized should be left unchanged.

<div class="attention">
Note that your solution would be checked against another random-generated input data - not the set presented to you!
</div>

Example:

    input data:
	1347
	0x80
	013
	101b
	
	answer:
	dec hex oct bin

Solution may start like:

	^0\d+ oct
	\d+ dec
	...

Use the button "RegExp" below to try your solution against sample input.

<script>
$(function(){selectLanguage('regexp');});
</script>
