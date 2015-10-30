_This problem is very similar to one given at [Facebook Hackercup](https://www.facebook.com/hackercup) event in Jan 2015 (qualification, problem #1).
We offer it to you so you can get better acquainted with problems of this popular contest and have greater motivation
to participate in future years._

<div class="centered">
<img alt="captain with a book weighting a rocket" src="http://s9.postimg.org/3u038phqn/star_captain2.png"/>
</div>

When merchant spaceship is fully loaded its total mass is expressed by long integer number, like `31415926`. The Ship's
Master want to tweak this value in documents to increase his profit, because both **tax** to be paid for the ship and
the **wages** he will receive for jounrney are proportional to this mass.

He discovered that if he only swaps two digits (not necessarily adjacent) - no one will notice this.

So he want to know two things:

- to which **smallest** value this number could be transformed by such a swap, to decrease tax he should pay;
- also to what **largest** value the number could be transformed, to increase the wages he is going to receive.

He can perform only one swap - and there is limitation that resulting value should not start with `0` (so its length
is decreased which could be easily noticed).

For the sample value given above the smallest value is `11435926` and the largest is `91415326`.

Note that input values will never start with `0` - thanks to [Nicolas Patrois](../user_profile/nicolaspatrois) for pointing out this bug!

**Input data** will have the total quantity of test cases in the first line.  
Next lines will contain a single integer each in hexadecimal (no longer than `30` digits, first of them is non-zero).  
**Answer** should contain a pair of `min` and `max` values for each mass in the input.

Example:

	input data:
	3
	302A
	10
	31415926
	
	answer:
	203A A023 10 10 11435926 91415326
