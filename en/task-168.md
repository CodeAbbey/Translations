Caesar is tired of enciphering his messages with his secret method (see [Caesar's Cipher](./caesar-shift-cipher) exercise).
He wants to use some device to automate the work.

However he had been living almost `2000` years before ordinary computers were invented so he can only use
[Brainfuck](../wiki/brainfuck)-based calculator left by UFO.

Please help him to create a BF program which can encrypt the line of text. You can base it on your solution for
[Copy Line](./copy-line) exercise.

You are allowed to use stack operations `#` and `$`.

**Input data** will contain a line of uppercase latin letters with spaces, terminated by single dot.  
**Answer** should give the encrypted line according to following rules:

- all letters are substituted by following ones in the alphabet (`Z` is substituted by `A`);
- whitespaces should not be encrypted;
- terminating dot should be ignored at all (it is only for the signal of the end).

Example:

    input data:
	THERE ARE ZOUNDS OF GAELIC WARRIORS.
	
	answer:
	UIFSF BSF APVOET PG HBFMJD XBSSJPST
