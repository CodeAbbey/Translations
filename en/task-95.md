Brethren of CodeAbbey are running several small businesses to support the Monastery. One of them is the **Winemaking**.

One of the interesting issues here is that the price of the wine is not constant. At some years customers are ready to
buy more barrels and pay higher, while at other years they are reluctant and brotherhood needs to lower prices to get
rid of wine stores.

It was found that the reason for such behavior is simple - after rainy years grapes yield wine of better quality and
people are more eager to purchase it.

This gives monks the idea - they need to find the formula for calculating more just price depending on weather records
from the preceeding year, so that trade will run more smoothly. *(the wine which is sold this year was prepared from
the grapes picked the year before)*

You are to help them in finding this formula. To keep things simple let us try approximating the dependency with the
linear function in the form

    Y = K * X + B

Where `X` is the amount of rainy days and `Y` is the price.

###Problem statement

You will be given a list of records, each containing the number of rainy days during previous year along with the
average price for which the wine was sold during current year.

Use the [Simple Linear Regression](http://en.wikipedia.org/wiki/Simple_linear_regression) and criteria of the
[Ordinary Least Squares](http://en.wikipedia.org/wiki/Ordinary_least_squares) to find parameters of the linear
function which can approximate the dependence between price and amound of rainy days.

**Input data** contains starting `A` and ending `B` year in the first line.  
Then lines follow for each year in form `YYYY: D P` where `YYYY` is the mark of year, `D` is the number of rainy days
(in previous season) and `P` is the wine price (in crowns per barrel).  
**Answer** should contain values for `K` and `B` with accuracy of `1e-7` or better.

Example:

	input data:
	1925 1947
	1925: 89 257
	1926: 75 226
	1927: 83 235
	1928: 52 173
	1929: 148 332
	1930: 109 268
	1931: 129 306
	1932: 115 289
	1933: 102 265
	1934: 99 269
	1935: 50 228
	1936: 102 265
	1937: 91 256
	1938: 79 238
	1939: 118 298
	1940: 134 311
	1941: 61 155
	1942: 146 340
	1943: 108 274
	1944: 96 242
	1945: 89 232
	1946: 143 328
	1947: 133 303
	
	answer:
	1.54053779316 107.312854273

*By the way, google for "wine price bordeaux linear regression" and you will see that the problem is not invented out
of nothing, but instead have similar real application.*