This problem is simple - you are given value `X` and you need to write a [Brainfuck](../wiki/brainfuck) program
printing squares of all integers from `1` to `X`.

At this time you can use "stack" with brainfuck. It is accessed with two additional commands:

- `#` pushes the value from current cell to stack (and its size grows while cells remain unchanged);
- `$` pops the value from the stack to current cell (stack size decreases and old value of the cell is lost).

It is handy in storing values temporarily. For example the task of copying value to neighbor cell could be solved
with just three commands `#>$`. However this feature is enabled only for specific tasks (like this).

**Input data** contain the single value `X` (not necessarily the same as given you for example when testing your code!).  
**Answer** should contain squares of integers from `1` to `X`.

Example:

    input data:
	5
	
	answer
	1 4 9 16 25

<script>
$(function(){selectLanguage('brainfuck');});
</script>