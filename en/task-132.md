<div class="centered">
<iframe width="320" height="180" src="//www.youtube.com/embed/elYw4Ve4F-I" frameborder="0" allowfullscreen></iframe>
<div class="hint">Infamous <span class="strong">Enigma</span> machine is also<br/>an example of sophisticated stream cipher</div>
</div>

*This task was inspired by the first exercise of the [Cryptography I](https://www.coursera.org/course/crypto) course
held by Stanford University at Coursera. However it is not exactly the same exercise and input data are surely different.*

[Stream cipher](http://en.wikipedia.org/wiki/Stream_cipher) is the core idea behind many encryption algorithms.
It consists of the following steps:

- **key** is chosen to be some lengthy (longer than encrypted message) sequence of values - it could be pseudo-random
    sequence or the codes produced by letters of some song, poem etc;
- each letter of the message is encoded (by some simple operation) with the corresponding value from the key sequence;
- result could be stored in form of such encoded values directly or converted to some more handy representation.

For examle, suppose we want to encrypt the phrase `Hello, World!` and we generate the key by the formula:

    key(i) = (i * 51 + 13) % 256

To be able to operate with letters we'll use their [ASCII](http://en.wikipedia.org/wiki/ASCII) codes. We'll use `XOR`
as operation to encode letter value with key value. And as for resulting values let's convert them to hexadecimal.

Here is what we get with such method:

	Letters:	H   e   l   l   o   ,       W   o   r   l   d   !
	
	ASCII:		72 101 108 108 111  44  32  87 111 114 108 100  33
	
	Key:		13  64 115 166 217  12  63 114 165 216  11  62 113
	
	Result:		69  37  31 202 182  32  31  37 202 170 103  90  80
	
	Hex:		45  25  1f  ca  b6  20  1f  25  ca  aa  67  5a  50

This encryption is strong as long as key generation algorithm is not too simple. However it could be easily broken if
we encrypt several messages with the same key sequence!

Now you are to try it yourself. Really there could be several approaches, but you are adviced to use the idea described
below.

What if we have two messages encrypted with the same key? We can `XOR` their bytes pair-wise to eliminate the values
of the key. Suppose that two original messages have letters `A` and `B` at some `i-th` position. Their encrypted
values became `A^K` and `B^K` where `K` is the key value for the same position. And if we `xor` them together:

    A^K  ^  B^K  = A ^ K ^ B ^ K = A ^ B ^ K ^ K = A ^ B ^ 0 = A ^ B

Of course the result we have - two letters xored - is not too informative. But what if one of the letters was a space?

We know that ASCII code for space is `0x20`, while codes for capital letters fall in range `0x40-0x5f` and for small
letters they fall in range `0x60-0x7f`.

This makes it possible to distinguish spaces in original lines (if we have more than two). And when we know position
of spaces, we can find out key values at these positions. Well, the rest is up to you!

<div class="attention">Note that you could not expect all bytes of the key to be found programmatically. So you will
probably get not completely decrypted message at first but then you will be able to substitute some missing or wrong
letters and find out more values of the key.</div>

**Input data** will contain the number of encrypted strings in the first line.  
Next lines will contain encrypted strings in form of hexadecimal values separated by dots.  
**Answer** should contain the decryption of the last string.

*For the sake of simplicity strings are stripped of any punctuations, so they contain only letters and spaces.
They are fragments of the famous text in English. On the other hand they are not necessarily whole sentences.*

Example:

    input data:
	7
	b7.1d.6c.c8.19.a7.1a.11.4f.86.16.c2.af.77.5f.2e.20.72.ad
	b6.10.71.91.4e.b5.1d.08.4c.ca.07.8d.ff.69.59.3a.29
	af.1d.7b.d5.19.a7.1c.11.5a.ca.10.8d.b9.63.55.29
	b5.10.7b.c3.5c.f4.1a.0f.1f.9e.1b.87.ff.77.45.2e
	b8.1d.72.dd.56.a3.53.0f.4a.88.1e.83.ad.6c.5e.29
	b6.11.72.d5.19.a6.1c.0f.5a.99.53.85.ad.6a.47
	88.58.7f.dc.19.bb.1d.5c.5b.9f.07.9b
	
	answer:
	I am on duty
