_We hope you have already solved [Mul Two](./mul-two) and get acquainted with basic operations on Intel 4004. This exercise
aims to teach you [jumping and looping](https://github.com/codeabbey/intel4004-emu/wiki/Jump-instructions). If this problem
looks too hard for you, try [Loops in Assembly](./loops-in-assembly) first._

Now we take part in development of brand new [Slot Machine](http://en.wikipedia.org/wiki/Slot_machine)
with Intel 4004 driving its logic. We were contracted to create
random number generator for it, since of course chip have no built-in randomizer.

After the night of deep thinking we came up with idea:

**Generate sequence of Fibonacci numbers, taking them `mod 128` to prevent unlimited grow**

Such sequence will look like:

	0 1 1 2 3 5 8 13 21 34 55 89 16 105 121 98 91 61 24 85 109 66 47 113...

You see, it looks randomly enough. So we only need to implement this algorithm. For now the goal is to calculate `i-th`
member this sequence (`0`-based) - later it could be adapted for any needs of slot-machine developers.

<div class="attention">You should submit valid source code for our Intel 4004 emulator - it would be interpreted and
run against several testcases. You could use input and answer boxes for your testing purposes.</div>

**Input** on program start the pair `r4:r5` will contain the value `i` (between `1` and `255`).  
**Result** should be stored in the pair `r0:r1`. Content of other registers is not important.

Examples:

    input:	  0 0 0 0 0 1 0 0 0 0 0 0 0 0 0 0
	result:   0 1 ...
	
    input:	  0 0 0 0 0 5 0 0 0 0 0 0 0 0 0 0
	result:   0 5 ...
	
    input:	  0 0 0 0 1 0 0 0 0 0 0 0 0 0 0 0
	result:   5 b ...

<script>
$(function() {selectLanguage('asm4004');});
var answerNotNeeded = true;
</script>
