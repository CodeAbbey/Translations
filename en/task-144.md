We have already some idea of **modular arithmetic** from the [Modular Calculator](./modular-calculator) exercise. Probably
you have noticed that we did not use division operation here. The second part of the 
[Modular Arithmetic](../wiki/modular-arithmetic) article in wiki explains why - this operation becomes a tricky one and
the result does not always exist at all!

_It is just the property of the math on such "modular fields" which makes them so attractive for cryptography
purposes - some common operations (inversion, calculating roots and logarithms) become significantly harder there!_

Now we are going to practice in this. If you are not acquainted with basics of modular arithmetic, please read
the article mentioned above.

We are going to solve the equation of the form:

    A * x + B = 0

in the finite field with modulo `M`, i.e. `Z/MZ`. Here `A` and `B` are constants, as usually.

As with conventional math we can rewrite the equation:

    A * x + B = 0
	A * x = -B
	x = -B/A
	x = -B * inv(A)

And here we obviously want to perform division via searching the **inverse** for `A`.

Straightforward but slow way is to iterate over the whole field of values, from `0` to `M-1` and check whether any
of them yields `1` when multiplied by `A`. However it becomes troublesome for values above billion (supposing that
computers nowadays can perform about `10` millions operations per second).

Another approach is to use the [Extended Euclidean Algorithm](./extended-euclidean-algorithm) (please solve this task
if you haven't done it still). Really, if we want to find inverse for `A` in the field with modulo `M` we should at
first check that

    gcd(A,M) = 1
	
since otherwise there would be no inverse at all. After that let us just plug these two values into **Bezout identity**
for which the **Extended Euclidean Algorithm** will find coefficients `a` and `b`:

    a*A  +  b*M   =   gcd(A,M)   =   1

Obviously if this equation is transferred to `Z/MZ` field we can simply strike out the `b*M` since
it is evenly divisible by `M`. Then we have:

    a*A  +  b*M   =   a*A   =   1

But this means that `a=inv(A)` - great! Of course if `a` happens to be negative we should "wrap" it around the lower
bound of the field, i.e. add `M` to it as many times as needed to make it fit into the range `0..(M-1)`.

###Problem Statement

So you are given values for `A` and `B` and your goal is to find `x` satisfying the equation.

**Input data** will contain the number of test-cases in the first line.  
Each case in the separate lines consists of three values `M A B`.  
**Answer** should give value `x` for each case or `-1` (not valid value) if solution do not exist.

Example:

    input data:
	3
	71 10 29
	57 42 30
	36 17 24
	
	answer:
	61 -1 24
