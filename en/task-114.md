To print `25` in [Brainfuck++](../wiki/brainfuck) we can use the following code:

    +++++ +++++ +++++ +++++ +++++ :

*Note: our version of Brainfuck uses two additional commands `:` and `;` to print and input cell value as decimal.*

It has `26` commands. Your task is to print `25` (or another value you will be given) using less commands.
However you could not print two digits separately:

    ++ : +++++ :

Because they will be separated with space.

You will be given a decimal value to print out.
Your task is to provide valid Brainfuck code which prints this value.
However your code should have less commands than this value.

**Input data** will contain a single decimal value between `25` and `90`.  
**Answer** - you can enter anything, for example the same value.  
**Solution** - should contain the required `Brainfuck++` code (unlike with other problems it would be checked).

**Important:** input is detached from the checker in this problem, so the solution like `";:"` will not be accepted.  
So your program should **input nothing** and just print out the required value.

*No example is given with this statement because otherwise it would be too generous hint :)*

You can use button "Brainfuck" below to run the code in **source** text area and see the result in **answer** field.

<script>
$(function() {selectLanguage('brainfuck');});
</script>