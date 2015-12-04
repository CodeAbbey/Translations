Recently CodeAbbey got functionality to determine user's country by IP. Each IP is in its core a kind of
imprecise internet address from which user's connection is coming to our server. All which is important to know - the
IP could be represented as `32`-bit integer (from `0` to `4294967295`).

_(please do not worry about privacy and conspiracy - you always can change the country to anything including `unknown`
in your profile settings if you really want to)_

This feature uses a list of IP-ranges, sorted in ascending order - and for each range of addresses some country is
assigned. This originally looks as following:

	range start		range end           country code
	-------------   ---------------     ------------
    0.0.0.0 		0.255.255.255			 US
	1.0.0.0 		1.0.0.255				 AU
	1.0.1.0			1.0.3.255				 CN
	
	...
	
	223.255.244.0	223.255.255.255			 AU
	224.0.0.0 		255.255.255.255			 US

Here IP-s are given in special ip format with `4` numbers for each byte (consisting of `8` bits).

When we have some unknown IP, like `178.66.68.158` (currently this is mine - and you can check yours with
[special tool](http://www.yougetsignal.com/what-is-my-ip-address/)) - we may use the following algorithm over this list:

- using [binary search](../wiki/binary-search) find the line `K` at which range-start is less or equal to given IP,
	while at line `K+1` range-start is strictly greater;
- check that given IP does fit between range-start and range-end of the `K`-th line and output the country code for
	this line (otherwise report the country is unknown).

_For those curious such (not very precise) lists could be found on internet freely (while more exact ones are to be
purchased, usually). I've downloaded one from [db-ip.com](https://db-ip.com/db/#downloads)._

###Problem Statement

You are given few thousands of IPs and you should return country codes for them. You will have only `1 minute` to
submit the answer, so probably it is better to use binary search rather than iterate through the list.

[Download our IP to Country list here](http://www.codeabbey.com/data/db-ip.txt)

_You may click it with the right mouse button and choose "Save As". Note that the file has unix-style line ends, so
some editors in windows could show it incorrectly, but you will anyway easily read separate lines programmatically._

The file has the slightly different format:

	0 9zldr US
	9zlds 73 AU
	9zlkw lb CN
	
	...
	
	1q5gzcw 2db AU
	1q5h1q8 8vn08v US

The integers of the first two columns are given in the numeral system with
[base 36](http://en.wikipedia.org/wiki/Base_36) (just to make them shorter) - so that for example in Python you may
use something like this to convert them to ints:

    s = '9zlkw'
	n = int(s, 36)

The first integer in the line is the **range-start** itself. The second is the **offset** of range-end:

    range_end = range_start + offset

For example in the second line offset is `73` which, converted to decimal, gives `255` - and you can check above that
this line really cares about IPs from `1.0.0.0` to `1.0.0.255`.

Of course you may preprocess this file after downloading (for example, converting values to decimals if you like etc) -
but it is not necessary.

**Input data** will provide the amount of IPs to be processed in the first line.  
Next lines will contain single IP each, also in `base-36`.  
**Answer** should give country codes for these IPs, as two-letter tokens separated by spaces.

<div class="attention">You have only about 1 minute to submit answer. Before processing input please
reload the page so that new set of data is generated and the timer is restarted.</div>

Example:

	input data:
	10
	1keei5f
	bixots
	1mmfpia
	dwaviz
	q0a5p9
	l600w7
	it4w75
	ht85qa
	1gvvigc
	hg8y3f

	answer:
	AU BJ TW IN GB GE US CA EC PT

<script>
noServerRun = true;
</script>