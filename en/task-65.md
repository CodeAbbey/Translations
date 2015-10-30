<!-- #Title -->
**Sweet Country** consists of several **Candy States**. You are given the list of the roads existing between these
states and now you want to improve logistics to deliver candies faster!

Your task is for any pair of statest to find the route with minimal number of roads and tell this number. For example
if `Carnival` is connected to `Maycorn` and this is connected to `Bawnty`, then route from `Carnival` to `Bawnty`
consists of `2` roads.

*You may want to build a transitive closure over the states map. For example with
[Floyd-Warshall](http://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm) algorithm.*

**Input data** will contain:

- the number of direct roads between states in the first line;
- the list of these roads, described by pairs of states (in separate line each);
- the number of routes to find (in separate line);
- the list of routes, described by pairs of states.

**Answer** should have lengths of routes, separated by spaces, or value `10000000` if no route exists between
the given states.

Example:

	input data:
	11
	Cowsome - Honepy
	Bawnty - Cowsome
	Lacry - Bawnty
	Honepy - Maycorn
	Maycorn - Bawnty
	Mikliday - Cowsome
	Mausse - Lednec
	Maycorn - Mausse
	Bawnty - Mausse
	Mikliday - Maycorn
	Lednec - Maycorn
	6
	Cowsome - Mausse
	Lacry - Honepy
	Bawnty - Honepy
	Mikliday - Mausse
	Honepy - Lednec
	Mikliday - Lacry
	
	answer:
	2 3 2 2 2 3
