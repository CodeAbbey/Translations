<div class="centered">
	<img alt="points inside and outside of polygon" src="http://s22.postimg.org/7m8suy169/ca_pip.png"/>
</div>

You perhaps remember the problem about [Frodo and Black Riders](./frodo-and-black-riders) - there we
were calculating area by [Monte-Carlo](http://en.wikipedia.org/wiki/Monte_Carlo_method) method. However, then
it was sufficiently easy to know whether point gets into area (visible to rider) or not.

In general the task of checking whether [point falls into the given polygon](http://en.wikipedia.org/wiki/Point_in_polygon)
is more complicated. And so here is the dedicated exercise for it :)

**Input data** consist of several parts:  

- in the first line there is a number `N` of the points described below;  
- then `N` lines follow with `X` and `Y` coordinates of the points - note that first and last are the same (i.e. they
	describe polygon with `N-1` sides);
- next follows the line containing `M` - the amount of sample points;
- and then `M` lines provide you `X` and `Y` coordinates of these random points.

**Answer** should contain `1`-based indices of the sample points which are inside the described polygon.

Note that all coordinates are integer for simplicity. Moreover, none of the sample points will have the same `X`-s or `Y`-s
as any of polygon corners.

Example (for picture shown above):

	input data:
	10
	10 5000
	3000 9950
	7000 9950
	9990 5000
	7000 50
	5453 4819
	6745 1403
	7144 9311
	3000 50
	10 5000
	12
	8354 7354
	8144 3649
	2714 2749
	9673 6106
	179 7081
	9202 3443
	1859 8863
	4940 4349
	8856 9648
	7692 5060
	5101 2511
	2052 2246
    
	answer:
	1 2 3 10 12
