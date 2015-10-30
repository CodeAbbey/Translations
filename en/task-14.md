This task provides practice for core property of remainder taking operation in arithmetic - persisting of the
remainder over addition and multiplication. This important property is often used for checking results of
calculations, in competitive programming, in calculation checksums and especially for encryption.  
See [Modular arithmetic][modar] for thorough explanations.

[modar]: ../wiki/modular-arithmetic

We have a kind of long arithmetic calculation here, and we are asked about the result modulo some number (`result % M` in many languages).

_If you are curious why modular arithmetic is that important, you can see
[Public Key Cryptography Intro](./public-key-cryptography-intro) and [RSA Cryptography](./rsa-cryptography) exercises._

**Input** data will have:

- initial integer number in the first line;
- one or more lines describing operations, in form `sign value` where sign is either `+` or `*` and value is an integer;
- last line in the same form, but with sign `%` instead and number by which the result should be divided to get the remainder.

**Answer** should give remainder of the result of all operations applied sequentially (starting with initial number)
divided by the last number.

_If you have troubles with this problem, please feel free to type its name in the "Search" box in the top menu and find relevant
topics at our forum - probably you will get enough enlightenment from there._

Example:

	input data:
	5
	+ 3
	* 7
	+ 10
	* 2
	* 3
	+ 1
	% 11
	
	answer:
	1

_In this case result after all operations applied sequentially is `397`_.

All numbers will not exceed 10000 (though intermediate results could be very large).
