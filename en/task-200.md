_Our colleague [Ashish Padalkar](../user_profile/ashish-padalkar) suggested that we should have famous Fizz-Buzz
in some form - so here it comes!_

This exercise on Intel 4004 Assembly language could be solved with the knowledge you already have, but probably
information about few [Special Instructions](https://github.com/CodeAbbey/intel4004-emu/wiki/Special-instructions)
could help to reduce the efforts and code size (so it would be wise to read this article).

###Problem Statement

FizzBuzz program probably came to fame after an article
**[Why can't programmers program](http://blog.codinghorror.com/why-cant-programmers-program/)** which stated
that of many applicants at programming job interviews only few can code this simple task:

**You are to print numbers from `1` to `N`, but instead of numbers which are multiples of `3` the word
`Fizz` should be printed - and instead of multiples of `5` - the word `Buzz`. If value is the multiple
of both - print `FizzBuzz` instead.**

So your goal is to write this in **Intel 4004 Assembly** language.

**Input data** consist of a single two-digit decimal `N` in range from `01` to `99`.  
**Answer** should give the sequence as described. All integers should be two-digit decimals also
and every element should be followed by single space (the last leading space is allowed).

Example:

    input data:   02
    answer:       01 02
    
    input data:   16
    answer:       01 02 Fizz 04 Buzz Fizz 07 08 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16

<script>
$(function() {selectLanguage('asm4004');});
var answerNotNeeded = true;
</script>
