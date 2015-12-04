<div class="text-center">
	<img alt="transport tickets with 6-digit numbers (USSR)" src="http://s5.postimg.org/mvi4t9pvb/talony.png"/>
	<div class="hint">Old tickets (perhaps from USSR times) with 6-digit numbers</div>
</div><br/>

When I travel over the city by public transport, I get the ticket which usually contains `6`-digit number and start
trying to build an arithmetic expression from this number according to following rules:

- between any two digits one of the operators `+`, `-`, `*`, `/` could be inserted - or these digits could be just
	"glued" together to form a larger value;
- brackets could be added to provide correct operations priority;
- the expression should yield `100` as a result.

For example, yesterday it was number `151374` which could be solved in several ways:

	1 + (5 + 1 + 3) * (7 + 4)  =  100
	(1 * 5) + (13 * 7) + 4  =  100

If ever I could not come up with solution I wonder, whether it is really not possible or I am just not smart enough.
So let us write the program to help checking this out. We will try to solve this for different target values,
not necessarily for `100`.

**Few restrictions:**
- let us agree that division could be used **only** if the first value is divisible by the second;
- please surround **every** binary operation by brackets to avoid priority issues (and help checking your expression) -
i.e. expression with `5` operators should have `5` opening and `5` closing brackets;
- unary minus operation is not allowed, though intermediate results inside expression could be negative.

**Input data** will contain amount of test cases in the first line.  
Next lines will contain test cases - the ticket number and the "target" value (separated by equals sign).  
**Answer** should contain proposed expression for each test case. If there is no solution - output zero. Separate
answers with spaces (but do not use spaces inside expression).

Example:

	input data:
	5
	151374=100
	256128=128
	577976=154
	942511=175
	767494=168
	
	answer: (1+((5+1)+3)*(7+4)) (256-128) ((((5*7)*7)-97)+6) 0 (((7-6)*74)+94)
