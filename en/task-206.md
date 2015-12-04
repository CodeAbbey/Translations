_This problem was "invented" while creating suitable encoding algorithm for using with certain functionality
of CodeAbbey site. Probably you can even find this functionality, though algorithm was slightly changed._

How attachments are transferred inside e-mails? Binary files contain many special byte values which could not
be represented easily in a text... Well, you probably heard that they are encoded using
[Base64](https://en.wikipedia.org/wiki/Base64). This system converts every `3` bytes of `8` bits each into
`4` visible symbols, taken from the alphabet of `64` characters (upper and lower Latin letters, digits and also
`'+'` and `'/'`). Each such symbol represents `6`-bit value in the range `0..63`. So we represent `24` bits
of the source message with `4*6` chunks instead of `3*8`.

You may play with such conversion with the help of some online tool [like this](https://www.base64encode.org/).

In some cases this system still is not convenient. For example, suppose we need to pass bytes in the URL, e.g.
paste it into browser address line. Here `'+'` and `'/'` have special meaning - and also uppercase letters could
be sometimes transformed into lowercase. Let us use `Base32` conversion instead! It will utilize the following
alphabet, consisting of `26` letters and `6` digits:

	ABCDEFGHIJKLMNOPQRSTUVWXYZ234567

We avoid digits `O` and `1` since they look similar to some letters. So it would be possible to encode every `5`
bytes (of `8` bits each) of the source message using `8` symbols (each representing `5`-byte value).

###Problem Statement

You need to write encoder and decoder for `Base32`. Please follow the specifications below.

Source message should be at first "padded" with one or more symbols so that its total length is a multiple of
`5`. These symbols should be just integer values showing how many symbols were added. I.e.:

	Hi			->	Hi333
	Bye			->  Bye22
	John		->  John1
	Abbey		->  Abbey55555
	Jeopardy	->  Jeopardy22
	CodeMasters ->  CodeMasters4444

With such padding we later will need only to peek at the last symbol to understand by which amount the string
should be reduced.

Then take every `5`-bytes chunk of the source message and write it down as bits (converting symbols to their
[ASCII](https://en.wikipedia.org/wiki/ASCII) values and then to binary octets). So that `John1` becomes:

	John1 => 74 111 104 110 49 =>
	
	01001010  01101111  01101000  01101110  00110001

Now this binary line is just glued together and split into chunks of `5`:

	01001  01001  10111  10110  10000  11011  10001  10001 =>
	
	  9      9     23     22     16     27     17     17

And with alphabet shown above it will be encoded as `JJXWQ3RR`.

We hope that you will be able to work out how to proceed with **decoding** on your own.

**Input data** will give total amount of test-cases in the first line.  
Next lines will contain one test-case each, of them odd lines (`1`-st, `3`-rd, `5`-th) will contain normal text
to be **encoded** while remaining will contain `Base32` data to decode.  
**Answer** should contain encoded and decoded phrases, all glued with spaces (it is not a problem that some
phrases contain spaces themselves).

Example:

    input data:
	6
	Ng Sir three
	ONUXIIDUNBZGKZJAMR2WK3DMNFXGOIDTNF2CAZDVMVWGY2LOM42DINBU
	Sir
	ONUXIIDUNBZGKZJAONUXIMRS
	blind Ng
	MJWGS3TEGU2TKNJV
	
	answer:
	JZTSAU3JOIQHI2DSMVSTGMZT sit three duelling sit duelling KNUXEMRS sit three sit MJWGS3TEEBHGOMRS blind

**Note:** please, try to avoid the idea of creating real binary string and splitting it with string functions.
This will work, but it would not be "production-ready" solution since it would be slow. Instead try to deal
with numbers (integers) directly.