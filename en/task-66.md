<!-- #Title -->
If you found the [Caesar's Cipher Decoding](./caesar-shift-cipher) task too primitive for your skills, here is more
complicated version: **Now you are to crack Caesar's Cipher**.

**Input data** will contain the number of encrypted messages in the first line.  
Next lines will contain the encrypted lines themselves. Each line is encoded with separate key!  
**Answer** should contain three first words of each decrypted line followed by the value of the key. Several answers
should be separated with spaces.

**Additional info**:

- the key will always be a value between `1` and `25` inclusive;
- lines will contain only capital latin letters and spaces to separate words;
- original messages are in English, from `60` to `100` characters long.

Example:

    input data:
	2
	XIP DBSFT PG ESFBNT
	VJQWIJ KV OCMGU VJKPIU XGTA SWGGT
	
	answer:
	WHO CARES OF 1 THOUGH IT MAKES 2

*You can find hints on algorithm in the
[Caesar Cipher Breaking with Least Squares](../wiki/caesar-cipher-breaking-with-least-squares)
though you are encouraged at least to try invent solution yourself...*