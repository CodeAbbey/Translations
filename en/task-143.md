We already have popular task about [calculating GCD](./greatest-common-divisor) of two integers.
Usual algorithm for programming this exercise is called **Euclidean**. Now we are going to study its extension.

###The goal

For any arbitrary `X` and `Y` it is easy to find `GCD(X,Y)`. Then we can write the following curious equation:

    a*X + b*Y = GCD(X,Y)

It is called [Bezout Identity](http://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity) and there is a theorem that
it is always possible to find **integer** values for `a` and `b` (not necessarily positive).

Though the sense of this equation is not self-evident, be sure it is of significant importance.

Now the **Extended Euclidean Algorithm** is just the tool to find these `a` and `b` efficiently.

###Algorithm

Remember how simple Euclidean Algorithm goes - we divide greater of two values by lesser and substitute it with the
remainder of this division, until the next remainder appears to be `0`. Then the preceding remainder gives the greatest
common divisor.

With extended version we use not only remainder, but also a quotient - and in addition two variables `S` and `T`.

When performing division, we write down both remainder `r` and quotient `q` and then update `S` and `T` using
quotient in a simple manner:

    Snext = Sprev - q * Scur
	Tnext = Tprev - q * Tcur

As you see we should remember not only current value of `S` and `T`, but also previous one. To initialize algorithm
we use:

    Sprev = 1
	Scur  = 0
	
	Tprev = 0
	Tcur  = 1

When the remainder reaches `0`, we get value for `a` from `Scur` and value for `b` from `Tcur` (supposing that we
started with `Y` as divisor). Let us see an example:

    X = 23, Y = 7,   GCD(23,7) = 1
	
	a*23 + b*7 = 1
	
	23 / 7  yields q = 3, r = 2
	Snext = 1 - 3 * 0 = 1,	Tnext = 0 - 3 * 1 = -3
		(reassignment)
	
	7 / 2	yields q = 3, r = 1
	Snext = 0 - 3 * 1 = -3,	 Tnext = 1 - 3 * (-3) = 10
		(reassignment)

	2 / 1   yields q = 2, r = 0
		(stop, print a = Scur = -3 and b = Tcur = 10)

after each iteration reassignment phase takes place which consists of the following assignments or shift of values
between variables:

	X <-- Y <-- r
	Sprev <-- Scur <-- Snext
	Tprev <-- Tcur <-- Tnext

We can test the results plugging them into Bezout Identity:

    -3 * 23  +  10 * 7  =  -69 + 70  =  1  =  gcd(23,7)

###Input and Output

**Input data** will contain the number of test cases on the first line.  
Next lines will contain a pair of values each.  
**Answer** should contain three values for each case - `r a b` separated with spaces - triplets themselves should
be separated with spaces also.

Example:

    input data:
	3
	23 7
	31132 24144
	22444 83452
	
	1 -3 10
	4 1807 -2330
	124 264 -71
