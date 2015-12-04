We are going to make extension for our site - to add problems which should be solved in
[Brainfuck](../wiki/brainfuck) programming language.

But of course we need an executing system (interpreter) for this funny esoteric language.

In this problem you should create such interpreter. Do not be afraid - it is easier to write Brainfuck interpreter
itself than to write Brainfuck problems for such interpreter.

We ask you to implement slightly altered version of the
language - **Brainfuck++** which includes two additional commands `;` and `:`.

Please, refer to the wiki article by the link above to read specification of the language.

**Input data** will contain two lines.  
The first input line contains Brainfuck program without any spare characters.  
The second line contains a sequence of numbers which would be consumed as input.  
**Answer** should contain output of the program.

Example:

    input data:
	;>;<[->+<]:>:
	3 5
	
	answer:
	0 8

<script>
$(function() {
    $('#run-brainfuck').hide();
});
</script>