The **Travelling Salesman Problem**, also known by abbreviation **TSP** has a very simple statement:

There is a Merchant (or Salesman) who wants to visit `N` cities (buying and selling goods there). The cities are
connected by the network of roads of the known length. We want to find the path consisting of `N-1` roads and visiting all `N` cities, which have minimum possible length.

Though the statement is short, the solution could be not that easy to find and implement. To demonstrate this, we'll
try to create program solving the TSP on a small network of `20` cities.

You should start from city `0` and finish anywhere you like, but all `20` cities should be visited, path should be
the chain of `19` roads and its length should be minimal. All roads would be bi-directional, i.e. graph is "undirected".

**Input data** contains `20` lines, each describing roads from the given city.  
Every line will start with the number of the city it is describing (just for convenience).  
Then several pairs of numbers will follow in the form `T:L` where `T` is the target city of the given road and `L` is
its length.  
**Answer** should contain `20` values describing the path - simply the numbers of the cities visited in proper order.

Example (for simplicity with only `7` cities):

    data:
	0 1:90 2:42 3:90 5:29 
	1 0:90 3:98 2:70 4:65 
	2 0:42 1:70 5:30 3:36 4:97 6:46 
	3 1:98 2:36 0:90 5:77 
	4 1:65 2:97 6:68 
	5 2:30 3:77 0:29 6:90 
	6 5:90 2:46 4:68 
	
	answer:
	0 5 3 2 6 4 1

*The path length in this example is `321`.*

Don't miss the similar problem with larger data-set and a challenge:
[Travelling Salesman Inverted](./travelling-salesman-inverted)!