This is an advanced version of the [Lucky Tickets](./lucky-tickets) problem.

Values here are going to be slightly greater so that it is not possible to use direct count of sums as you probably did
and some "dynamic programming" approach should be invented.

<div class="attention">
Please note that result could be long enough and some languages have no built-in abilities to store such values. E.g. with
<code>C++</code> neither <code>long long</code> nor <code>double</code> will do. You may prefer to switch to
<code>Python</code> or <code>Java</code> temporarily, or implement "long arithmetics" representing values as arrays in such case.
</div>

**input data** contains two values: `N` - the length of the ticket number and `B` - the base of numeral system.  
**answer** should contain the amount of lucky tickets.

*Note: to simplify the matter, `N` is always even and `B` do not exceed `9`.*

Example:

	input data:
	22 8

	answer:
	2719720106419046288
