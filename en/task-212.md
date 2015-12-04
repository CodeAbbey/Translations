**Important:** please, download the latest version of our [Intel 4004 emulator](https://github.com/CodeAbbey/intel4004-emu/) for previous have subtraction operation
implemented incorrectly and you may want to use it.

Early CPU's often lacked multiplication and especially division operation. This made conversion between binary and
decimal systems quite a tough challenge - and lead to widespread of BCD format, when every `4-bit` nibble stored one
decimal digit.

In this problem we are to write code for Intel-4004, converting 4-digit value from BCD to Hexadecimal format.

**Input** will have 4-digit BCD value in `r3:r0` (note that it is "reversed", i.e. `r3` is the most significant).  
**Output** should give 4-digit Hex value in `r11:r8` (where `r11` also is the most significant).

Example:

	input:    1 2 3 9 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   0 0 0 0 0 0 0 0 9 6 4 2 0 0 0 0

Note that the checker will not care about registers other than `r11:r8` so they could contain anything after calculations.

Answer is not tested by the checker and the input serves only as a sample. You rather need to supply working code which
will be executed against several test-cases on the server.

**The size** of solution is measured in the bytes. Many instructions are single-byte, while some (especially jumps)
are two byte long. Also if you add data in your program via `db` instruction - the size is of course increased.
To check the size you may use our [online emulator](http://www.codeabbey.com/index/wiki/intel-4004-emulator).

<script>
$(function() {selectLanguage('asm4004');});
var answerNotNeeded = true;
</script>
