_This problem is a modification of the similar exercise from Stanford-online
[course on Cryptography](https://www.coursera.org/course/crypto)._

If after solving [RSA cryptography](./rsa-cryptography) exercise you still have vague idea of security of the **RSA**
algorithm here is a variation of the same problem.

You are again to decrypt the encoded message but now instead of `p` and `q` you are given only their product `n`, just
as a real attacker. Encryption was still performed with `e=65537`, but unfortunately you have no idea of the decryption
exponent `d`!

However by chance you know that the person who encrypted the message was a perfect noob and used close values of `p` and
`q`, so you may find a way to factorize `n` easily enough.

Conversion between string and number is performed in the same way as in the RSA-related exercise mentioned above.

**Input data** will contain `n` in the first line.  
The second line contains `cipher` which was generated as `a^65537 mod n` where `a` is the original text converted to
long integer.  
**Answer** should contain the deciphered text.

Example:

	input data:
	2005386240811006492510206908835874977464399827995998174235015291258133373258958037573585627
	258926557618335589879504876460462075566410747651590614428022205934562315249635550863811428
	
    answer:
	EGG EAT SKI SHY ARM EON HIP FUN LOW

_**Hint:** The name of **Pierre de Fermat** is presented in the title intentionally, so some googling may help..._
