This problem is an ideologically inverse to [Travelling Salesman](./travelling-salesman).

The salesman has a map of cities (the graph). Salesman works on behalf of the company, so he is not interested in
maximizing sales etc. However he can save some money on each transition from city to city (by purchasing cheaper
ticket or something like this) and he wants to know how much money he can save for himself.

There are `100` cities. Some of them are connected with roads - and all roads could be travelled only one-way (because
there are no train or airplain routes going backward usually).

For each of road you will be told an amount of money which could be saved.

Salesman **does not need** to visit **all** cities, however the more he visits - the more money he will save. Of course
he could not visit the same city twice.

**Input data** contain number of cities and the number of roads in the first line.  
Next lines contain roads description - names of two cities (source and destination) and the amount of money.  
**Answer** should contain a chain of city names (starting anywhere you like) describing the route.

**NOTE** - this task is the `challenge` so you will gain some score from `0` to `1` depending on amount of saved money:

    score = collected_money / (6 * 99)

Here `6` is the maximum amount of money which could be saved on any road and `99` - maximum amount of roads which could
be traversed. The score is multiplied by fixed challenge coefficient and added to your Enlightenment.

For this task the input is not random - all users see the same data.

Example:
	
	input data:
	100 2000
	BA DE 5
	BA XO 6
	BA NE 5
	BA DO 6
	...
    ZU PU 5
	ZU QE 6
	ZU PA 4
	
	answer:
	BA DE ZE FU VA GA JU RA PE PI HU GE ME KE

Such answer will give you a score about `0.113`.
