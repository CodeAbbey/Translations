<div class="centered hint">
	<img alt="Sid Meyer's Civilization - Steam Engine Discovery" src="http://s24.postimg.org/dwxz560r9/civ_se.png"/><br/>
	<span>So research on Steam Engine requires Physics and Invention and is necessary for RailRoads.</span>
</div>

Have you ever played [Sid Meyer's **Civilization**](http://en.wikipedia.org/wiki/Civilization_(video_game))? It was a
wonderful strategy game where you were founding and growing cities, exploring and colonizing the world, and making
**discoveries and inventions**. This was an essential part of the game - certain discoveried technologies allowed you
to create new types of buildings and weapons - and what is important - to investigate newer technologies.

For example:

- **MapMaking** (requires **Writing**, allows **Navigation**) gives you power to build triremes and explore ocean,
	eventually visiting other continents;
- **Navigation** (requires **MapMaking** and **Astronomy**, allows **Physics** and **Magnetism**) makes possible
    building more reliable ships;
- **Steam Engine** (requires **Physics** and **Invention**, allows **RailRoads**) - with it you can create
	protected ironclads.

The game had the built-in "civilopedia" which described briefly the meaning of each "civilization advances" and showed
their requirements and opportunities. If we think of each discovery as of a `node` - then the requirements between them
will be directed `edges` - and so the whole "science" could be represented as a graph.

It is important that such graph have no cycles (otherwise certain discoveries could never be made) - i.e. it is an
example of a [directed acyclic graph](http://en.wikipedia.org/wiki/Directed_acyclic_graph) (abbreviated as DAG).

Suppose we marked each discovery with some two letter code, like `Mm` for MapMaking or `Se` for Steam Engine and wrote
down all requirements (i.e. edges of a graph) as pairs, like this:

    Wr -> Mm
	Mm -> Na
	As -> Na
	Na -> Py
	Py -> Se

and now we want to put these discoveries into a list in such an order, that as we achieve them sequentially one by one
starting from the top, we'll never encounter a problem of unsatisfied prerequisites. I.e. when we are going to work
on each next technology, we found that all necessary preceding discoveries and inventions have been made already.

Such ordering is called a [topological sorting](http://en.wikipedia.org/wiki/Topological_sorting) - as you see it has
great importance in planning tasks or activities which have dependencies between them.

**Input data** will contain the amount of discovery code pairs in the first line.  
Next lines will contain two discovery codes each - so that first is required to start working on the second.  
**Answer** should give a list of codes ordered according to topological sorting. (any such ordering is
acceptable if there are more than one)

Example:

    input data:
	5
    Wr Mm
	Mm Na
	As Na
	Na Py
	Py Se
	
	answer:
	Wr As Mm Na Py Se
