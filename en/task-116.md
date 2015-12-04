It is easy to sum two numbers in **Brainfuck**, for example by code like this:

    ;>;        input two numbers into cells 0 and 1
	[          while the number in the cell 1 is not zero
	    -      decrement cell 1
		<      shift to cell 0
		+      increment cell 0
		>      shift back to cell 1
	]
	<:         shift to cell 0 and print the result

This task is only a bit more tricky. You need not only to get the sum of two values, but also keep these values.
More exactly:

<div class="attention">Please note that stack operations are not enabled for this task. Otherwise it would be too trivial! :)</div>

**Input data** has two values `A` and `B` in the single line.  
**Output** should have the sum `A+B` printed into it.  
**Additionally** after the stop the program should have values `A`, `B`, `A+B` in the cells `0`, `1` and `2` respectively.

*This problem is not that important by itself, but it shows quite important trick which may be used in building up
more complicated programs in future.*

<script>
$(function() {selectLanguage('brainfuck');});
</script>