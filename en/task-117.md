The language is called [Turing-complete](http://en.wikipedia.org/wiki/Turing_completeness) if it allows any possible
program to be written (at least hypotetically).

Brainfuck belongs to this class of languages. However this do not mean there are simple ways to write simple programs :)

As an example we'll try to solve the following problem:

**Write [Brainfuck++](../wiki/brainfuck) program which inputs number and divides it by two.**

As a hint think of the simple loop:

    [-]

it allows you to decrement the value of the current cell to `0`, possibly performing some additional operations (we
have already used it to sum and copy values). You should add to this loop some code which behaves differently on
even and odd operations. As an example you can thing of the expression like this:

    x = 1 - x   # it is an assignment, not equality

after execution `x` becomes `1` if it was `0` and vice versa.

**Input data** will contain an integer value `N`. <span class="red strong">Note: </span> testing will be performed with
values different from which was generated for you as an example.
  
**Answer** should contain the quotient and remainder of division this value by two, i.e. `N/2` and `N%2`.

Example:

    input data:
	13
	
	answer:
	6 1

<script>
$(function(){selectLanguage('brainfuck');});
</script>