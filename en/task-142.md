Probably you have already solved [Sliding Window Search](./sliding-window-search) task. Now we are going to see how this
idea of encoding repetitive substrings with back references in form `length-offset` is used for compression.

_The algorithm described below is an implementation of [LZ77](http://en.wikipedia.org/wiki/LZ77_and_LZ78)
proposed by Israeli scientists **Lempel** and **Ziv**
in `1977`. Later many other algorithms were built from this idea (`LZSS` and `LZW` for example) - and most of
contemporary archivers use some of its derivatives (including `zip` compressor and `gif` image format)._

You will be given the sequence of bytes of already compressed data and your goal is to decompress it to original.

The encoding scheme used was the following:

- if back reference of `length` characters was found at some `offset`, then two bytes are stored just as in the previous
	task (i.e. `(length << 12) + offset` with most significant byte first);
- otherwise (even a single character could not be found in preceding block) this character itself is written preceeded
	by byte with value `0` to distinguish these two bytes from normal `length-offset` pair.

By these rules the word `ABRACADABRA` is encoded as:

	00 41
	00 42
	00 52
	10 02
	00 43
	10 01
	00 44
	40 06

**Input data** contain a sequence of bytes in hexadecimal format. There are about `4.5kB` of encoded data.  
**Answer** should contain the decoded text. It should be about `7kB` long.

Example:

    input data:
	00 69 00 6e 00 74 00 65 00 72 00 70 10 01 10 03 30 05 00 20 50 06 10 0f 00 64 00 73
	10 08 10 05 00 6f 10 02 90 17 10 09 20 03 20 06 40 0d 10 17 60 09 00 6d 00 61 30 21
	
	answer:
	interpreter pretends to interpret reprinted reprimands

_**Note:** we do not require you to write a compressing algorithm (though we are going to have such exercise for
`LZW` later) - but you nevertheless can try to create your own archiver!_