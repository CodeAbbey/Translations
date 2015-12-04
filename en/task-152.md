You are probably already get a clear idea on principle of **Public Key Cryptography** from the
[exercise on ElGamal method](./public-key-cryptography-intro).

Here is another method (perhaps, more famous) named [RSA](http://en.wikipedia.org/wiki/RSA_(algorithm)) after its three
authors. It was proposed in `1977` i.e. `8` years earlier than ElGamal's - though the latter is really an adaptation
of curious [Diffie-Hellman](http://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) algorithim for key
exchange which was published in `1976`.

###Algorithm idea

It is based on [Euler's theorem](http://en.wikipedia.org/wiki/Euler's_theorem) which states that for
modular exponentiation with modulo `n` it is very easy to compute the power equal to `phi(n)` for any base `a` coprime
with `n`:

    a ^ phi(n) = 1

For example for `n=391` almost any `a` raised to power of `phi(n)=352` yields `1` (except for multiples of `17` or `23`).

How can we use it?

Suppose we choose a pair of values `e` and `d` such that

    e*d = k*phi(n) + 1

since such a whimsical choice gives us an interesting property:

    (a^e)^d  =  a ^ (e*d)  =  a ^ k*phi(n) + 1  =  a * (a ^ phi(n))^k  =  a

So if we want to encrypt value `a` we can raise it to the power `e`. And if we want to decrypt it we should raise it
to the power `d`:

    cipher = a ^ e
	a = cipher ^ d

The last thing to explain is how to choose a pair of `e` and `d`. Well, `e` could be any arbitrary prime and then `d`
is calculated as its inverse modulo `phi(n)`:

    d = inv(e)  | mod phi(n)

But how to make this approach "strong" against attacking? Attacker will know `e` and `n` (they are parts of **public
key**) but to decrypt the `cipher` he needs to take `e-th` root of it, which effectively means to find `d`!

It is easy to calculate `d` if one knows `e` and `phi(n)`. However suppose that `n` is the product of two large primes
`p` and `q`, then:

    n = p*q
	phi(n) = n - p - q + 1

But poor attacker may not know these `p` and `q`. So really the problem of breaking this cipher is the same as
problem of [factorization](./integer-factorization) which currently have no general efficient solution for numbers
built of large prime factors (and scientists believe such solution does not exist so the method is safe).

_Resulting algorithm surprizingly works even when `a` is not coprime with `n` - you may investigate this case yourself!
Anyway in practice it is highly improbable case._

###Problem Statement

Now we are going to write a program to perform **RSA** decryption - it will give us necessary experience before trying
to hack this algorithm!

The text string is encoded as a long integer using the following approach:

- for each letter its two-digit decimal [ASCII](http://en.wikipedia.org/wiki/Ascii) is written (so text will not use
	symbols with codes greater than `99`);
- these two-digit values are simply concatenated;
- then `00` followed by several randomly choosen digits is added to the tail.

For example the word `ABBA` could be encoded as `6566666500314`:

	A    B    B    A  | end | few random digits
	-----------------------------------
    65   66   66   65 | 00  | 3   1   4

This integer is then encrypted by `RSA` and you should decrypt it back and print the original text string.

_Adding some randomization is crucial for any public key cryptography system to prevent attacker guessing the original
message by trying to encrypt his guesses himself._

**Input data** will contain `p` and `q` at the first and second lines, while for `e` we choose popular constant value `65537`.  
The third line will contain the long integer value of `cipher`.  
**Answer** should contain the decrypted text string.

Example:
	
	input data:
	30762542250301270692051460539586166927291732754961
	29927402397991286489627837734179186385188296382227
	424236952206057066872700453503661773567827006571091351397488406910437574827532103275742945321419387
	
	answer:
	TOWEL BEANS SWORD STOCK STORM CHECK

**P.S.** you may say _It is so easy to decrypt - not a problem at all!_ - but remember that attacker do not know `p`
and `q` and instead has only their product `n`. Follow to the [task on hacking RSA](./fermat-goes-hacking-rsa) to feel
yourself as a hacker!