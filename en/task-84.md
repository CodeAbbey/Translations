<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="600px" height="140px">
	<g transform="translate(50,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 10,50 L 60,10 180,10 230,50 180,80 180,10 100,110 110,50 60,10 100,110 40,80 60,10"/>
			<path d="M 10,50 L 40,80 30,130 100,110 180,80 230,130"/>
		</g>
		<g stroke="#77ff77" stroke-width="2" fill="none">
			<path d="M 10,50 L 60,10 180,10 230,50"/>
			<path d="M 60,10 L 110,50"/>
			<path d="M 180,10 L 180,80 230,130"/>
			<path d="M 10,50 L 40,80"/>
			<path d="M 180,10 L 100,110 30,130"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="60" cy="10" r="8"/>
			<circle cx="180" cy="10" r="8"/>
			<circle cx="10" cy="50" r="8"/>
			<circle cx="40" cy="80" r="9"/>
			<circle cx="110" cy="50" r="8"/>
			<circle cx="30" cy="130" r="8"/>
			<circle cx="100" cy="110" r="8"/>
			<circle cx="230" cy="130" r="8"/>
			<circle cx="180" cy="80" r="8"/>
			<circle cx="230" cy="50" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="60" y="10">2</text>
			<text x="180" y="10">4</text>
			<text x="10" y="50">1</text>
			<text x="40" y="80">10</text>
			<text x="110" y="50">3</text>
			<text x="30" y="130">7</text>
			<text x="100" y="110">8</text>
			<text x="230" y="130">9</text>
			<text x="180" y="80">6</text>
			<text x="230" y="50">5</text>
		</g>
	</g>
</svg>
</div>

*Note: to start work on this task you need to solve [Graph Generator](./graph-generator) to generate input data.*

**Dijkstra's algorithms** solves very popular task - it allows to find the sortest paths from the given node of
a graph to all other nodes.

Of course this can find applications in logistics etc., but far more common usage is in communication networks.

For example, think of [Zig-Bee](http://en.wikipedia.org/wiki/ZigBee) network, consisting of `N` modules. These small
devices are capable of determining the shortest route to destination extremely fast, notwithstanding that the
network geometry can change over time - some modules can go offline, some other could be installed on vehicles etc.
So most routers in almost every network technology utilize this method or some derivative
(like [A\*](http://en.wikipedia.org/wiki/A*_search_algorithm)).

In this task you are to implement Dijkstra's algorithm - the details you can find in the corresponding
[Wikipedia article](http://en.wikipedia.org/wiki/Dijkstra%27s_algorithm).

The simplest form (without min-priority queue) would be sufficient.

The graph is described the same way as in [Graph Generator](./graph-generator) problem - by specifying the number of
vertices and the seed for randomizer.

For example, if we use the same graph with `10` nodes and initialize random generator with the same seed `0` and will
run the Dijkstra's algorithm starting from node `1`, we'll get the following paths to each of destinations:

    dest.          path            length
	  1            1                  0
	  2            1-2                1
	  3            1-2-3              2
	  4            1-2-4              2
	  5            1-2-4-5            5
	  6            1-2-4-6            9
	  7            1-2-4-8-7          4
	  8            1-2-4-8            3
	  9            1-2-4-6-9         16
	  10           1-10               3

The tree of these paths is marked with green lines in the picture above.

**Input data** will contain three numbers `N` - the number of nodes, `X0` - seed for random generator and `S` the
index of starting vertex (from where we are to search for paths to others).  
**Answer** should contain the route length to each vertex in the graph.

Example:

    input data:
	10 0 1
	
	answer:
	0 1 2 2 5 9 4 3 16 3

*Attention: the length of the answer will be several kilobytes long - not very much, so it would give you no problem
when copying and pasting it - but take care not to truncate it accidentally.*