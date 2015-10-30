This is a first exercise on Assembly for Intel 4004. Make sure to browse [tutorial](https://github.com/codeabbey/intel4004-emu/wiki)
for first few pages (including "assignment" and "arithmetic" instructions). You may use built-in emulator (with the button
below source area) - or download interpreter written in Python [from here](https://github.com/codeabbey/intel4004-emu).

Your goal is to multiply the value in registers `r0:r1:r2:r3` by two - i.e. duplicate this 16-bit number
(with least significant bits in `r3` and most significant bits in `r0` - we call such arrangement
[big-endian](http://en.wikipedia.org/wiki/Endianness) which is "more human", but perhaps somewhat illogical).

For example, the following code allows you to duplicate the single register `r0`:

    ld r0		; load R0 to Acc
	clc			; clear Carry flag
	add r0		; add R0 to Acc
	xch r0		; exchange value of Acc with R0

However this code duplicates only one of registers and it is not the most elegant / efficient approach.

**Input and Answer** for this problem are necessary only for running emulator. You may see that input is given in
form of `16` hexadecimal digits. When emulator sees input data in that form, it loads them into its `16` registers (instead
of using as console input). Output will also be given to you as values of registers. You can change these digits as
much as it is needed for your testing purposes.

**Important** the real answer is the source you submit. It will be executed on server against several test-cases to
judge whether it is correct.

Examples:

    input:    0 0 0 1 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   0 0 0 2 0 0 0 0 0 0 0 0 0 0 0 0
	
    input:    0 0 0 3 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   0 0 0 6 0 0 0 0 0 0 0 0 0 0 0 0
	
    input:    0 0 0 5 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   0 0 0 a 0 0 0 0 0 0 0 0 0 0 0 0
	
    input:    0 0 0 a 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   0 0 1 4 0 0 0 0 0 0 0 0 0 0 0 0
	
    input:    3 b 8 a 0 0 0 0 0 0 0 0 0 0 0 0
	answer:   7 7 1 4 0 0 0 0 0 0 0 0 0 0 0 0

<script>
$(function() {selectLanguage('asm4004');});
var answerNotNeeded = true;
</script>