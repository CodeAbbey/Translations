Tickets in public transportation system have unique numbers. We have a funny superstition or omen about them:

**If the sum of digits in the first half of number equals to sum of digits in the second half - such ticket is
concidered "Lucky" - one should at once recollect some long-wished dream and eat this ticket - then the dream
surely will come to reality!**

Number is split into halves of equal length, of course. If the number contains an odd amount of digits - the middle
of them is simply ignored. So the numbers like `117234` or `4493278` are examples of lucky ones:

    1 + 1 + 7 = 2 + 3 + 4 = 9
	4 + 4 + 9 = 2 + 7 + 8 = 17   (3 is ignored)

*Of course the number may have trailing zeroes, for example `6-digit` numbers start from `000000`, `000001` and end
with `999998`, `999999`.*

We are going to undertake a great reform - ministry of transportation wants to create tickets with new number format -
it would contain `N` digits, each of them in numeral system with base `B`. Numeral systems of up to hexadecimal
would be used (i.e. `B <= 16`) and numbers could be of up to `24` digits.

You are to count how much "lucky tickets" exist for given pair of `N` and `B`. You may safely assume that numbers with
great value of `N` will use smaller values of `B` to simplify the matter for you.

**Input data** contains the number of test-cases in the first line.  
Next lines contain a pair of values `N` and `B` each.  
**Answer** should contain the amount of lucky tickets for each case:

Example:

    input data:
	4
	1 5
	4 3
	5 2
	6 10
	
	answer:
	5 19 12 55252

*If you have found this problem too easy, try an [Lucky Tickets Advanced](./lucky-tickets-advanced)*