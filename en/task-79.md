The King of Ruritania seeks for a way to reduce funding on road maintenance in his kingdom.

Kingdom of Ruritania consists of several cities connected by several roads. Each road connects only two cities, and
for any pair of cities there exists at least one way between them (the way could be a chain of several roads).

The King just have come to the bright idea - if there is any cycle (or loop) in the road network, then between some
cities there exist more than one way (*for example between two cities in this cycle you can travel either clockwise or
counterclockwise*) - so, obviously, at least one road could be removed and cities will nevertheless remain connected.

Your task is to help the King in finding whether the road map contains cycles or not.

**Input data** contains the amount of test-cases in the first line.  
Next lines contain one road map each - it starts with the number of roads in this map followed by road descriptions
in form `A-B` meaning that the road connects cities `A` and `B` (all places are named with a single capital letter).  
**Answer** should have `0` for maps with no cycles and `1` for maps which could be "optimized".
As usual, separate values with spaces.

**Note:** there will be no roads connecting the city to itself.

Example:

    input data:
	3
	3 A-B B-C B-D
	4 A-B B-D D-C A-C
	4 A-B B-C C-A A-D
	
	answer:
	0 1 1
