<!-- #Average of an Array -->
Important branch of mathematics which heavily uses programming is statistics - i.e. calculation of characteristics
for some data. (Just think of statistics of visitors / pageviews of the web-site etc.)
Learning this discipline is usually started from acquaintance with an **average value**.

Average (or mean) value of some numbers could be calculated as their sum divided by their amount. For example:

    avg(2, 3, 7) = (2 + 3 + 7) / 3 = 4
	avg(20, 10) = (20 + 10) / 2 = 15

You will be given several arrays, for each of which you are to find an average value.

**Input data** will give the number of test-cases in the first line.  
Then test-cases themselves will follow, one case per line.  
Each test-case describes an array of positive integers with value of `0` marking end. (this zero should not be
included into calculations!!!).  
**Answer** should contain average values for each array, rounded to nearest integer (see [task on rounding](./rounding)), separated by spaces.

Example:

    input data:
	3
	2 3 7 0
	20 10 0
	1 0
	
	answer:
	4 15 1
