_Solving [Loops in Assembly](./loops-in-assembly) first may help you to prepare for this problem better._

Let us now learn [extensions for working with console](https://github.com/CodeAbbey/intel4004-emu/wiki/Extensions-and-Limitations)
which our emulator provides. Please note that such input-output operations are dependent on specific hardware implementation
(i.e. how Intel 4004 CPU and other chips are connected to keyboard and display, types of these peripherals etc) - so if you
ever get real device with `c4004` inside, you should not expect these extensions to work in the same way.

So we have two of them:

- calling fake subroutine at address `$3f0` reads a character into `r2:r3` register pair;
- calling another one at address `$3e0` prints the character from the same registers.

I.e. if we write a simple program:

    loop:
	jms $3f0
	jms $3e0
	jun loop

It will copy data from standard input to standard output without termination.

###Problem statement

The goal is to write a program which:

- reads character from standard console;
- writes their hex representation (two digits for each);
- stops on encountering new-line.

What we'll see in `r2:r3` after reading a character? It is `8-bit` [ASCII-code](https://en.wikipedia.org/wiki/ASCII) - for
example it would be `$21` for `"!"`, `$30` for `"0"` and `$41` for `"A"` (their decimal values are `33`, `48` and `65`).

So for each char you read, you need to convert its higher and lower nibbles (values of `r2` and `r3`) into code of
respective character from set `0123456789ABCDEF`, load this code into the same pair again and call print. You may stop
when you read a character whith higher nibble equal to `0` (it is either new-line with code `$0A` or carriage-return with
code `$0D`).

_**Note** that for this problem input is not given as sequence of `16` digits as for previous tasks, so it is not regarded
as initial states of registers and instead is simply used to feed your program from virtual console._

<div class="attention">Your solution should be a valid source for Intel 4004 emulator!</div>

**Input** would be short text string.  
**Output** should contain hex codes of the characters of the string.

Examples:

    input:    A0!
	output:   413021
	
	input:    Hi, People
	output:   48692C2050656F706C65

<script>
$(function() {selectLanguage('asm4004');});
var answerNotNeeded = true;
</script>
