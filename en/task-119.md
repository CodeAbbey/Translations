Probably you either know about [Fibonacci sequence](./fibonacci-sequence):

- you are given two initial values `f[0]` and `f[1]`;
- each of the following values is just the sum of two preceeding, i.e. `f[k] = f[k-1] + f[k-2]`.

An example starting with initial values of `0` and `1` produces the following:

    0 1 1 2 3 5 8 13 21 ...

Here is a small challenge for you - implement this algorithm in Brainfuck. We believe it would be a simple exercise
and almost all who try it will be able to game the same or similarly high score!

<div class="attention">Please note that stack operations are disabled for this problem - otherwise
it would be less "challenging", you see :)</div>

**Input data** will contain three values `N`, `f0`, `f1` - the amount of elements to generate to two initial members.  
**Answer** should give precisely `N` values of the sequence.

Example:

    input data:
	5 1 3
	
	answer:
	4 7 11 18 29

You may safely assume that none of input values will exceed `15` and that `f0 < f1`.

**Challenge result** is assessed by the following formula:

    $len = length(your_solution)
    $score = (45 - $len) / 20

"Length of your code" counts only commands, so you may put any amount of comments and spaces freely. So you'll get
`0.0` score for solution of `45` commands and `1.0` score for solution of `25` commands.

<script>
$(function(){selectLanguage('brainfuck');});
</script>