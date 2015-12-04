<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="160">

<g fill="none" stroke-width="3" transform="translate(150,0)">
	<path d="M 30,50 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 80,50 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 130,50 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 180,50 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 230,50 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 280,50 v -30 l 25,-15 l 25,15" stroke="black"/>

	<path d="M 5,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 55,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 105,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 155,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 205,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 255,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 305,95 v -30 l 25,-15 l 25,15" stroke="black"/>
	
	<path d="M 30,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 80,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 130,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 180,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 230,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	<path d="M 280,140 v -30 l 25,-15 l 25,15" stroke="black"/>
	
	<path d="M 5,95 l 25,15" stroke="black"/>
	
	<path d="M 30,140 l 25,15 l 25,-15" stroke="black"/>
	<path d="M 80,140 l 25,15 l 25,-15" stroke="black"/>
	<path d="M 130,140 l 25,15 l 25,-15" stroke="black"/>
	<path d="M 180,140 l 25,15 l 25,-15" stroke="black"/>
	<path d="M 230,140 l 25,15 l 25,-15" stroke="black"/>
	<path d="M 280,140 l 25,15 l 25,-15" stroke="black"/>
	
	<path d="M 330,140 v -30 l 25,-15 v -30" stroke="black"/>
	<path d="M 330,50 v -30" stroke="black"/>

	<g stroke="blue" stroke-width="2">
		<text x="175" y="85" stroke="red">X</text>
		<text x="225" y="85">A</text>
		<text x="200" y="40">B</text>
		<text x="150" y="40">C</text>
		<text x="125" y="85">D</text>
		<text x="150" y="130">E</text>
		<text x="200" y="130">F</text>
	</g>
</g>

</svg>
</div>

Many computer games are played by moving some pieces or heroes over a map or a field of some kind. There are two
popular kinds for geometry of such maps:

- rectangular grid - the field is tiled by rectangles or squares;
- hexagonal grid - the field is tiled by hexagons.

Well-known game [Heroes of Might and Magic](http://en.wikipedia.org/wiki/Heroes_of_Might_and_Magic) for example
utilized both variants - **rectangular** grid is used on the world map while riding between castles (with ability of
diagonal movements), while **hexagonal** grid is used as a battle field in combat mode.

Hexagonal tiling looks more beautiful for user, but the programming its geometry is slightly more tricky. That is
what we are going to practice now.

**Problem statement**

Suppose the "hero" is placed at some cell of hexagonal grid. Then he can move in six directions. On the
picture above `X` marks the initial cell and letters `A`, `B`, `C`, `D`, `E`, `F` - the possible movements for `1`
step. `A` moves the hero directly to the right and other directions are named in the counter-clockwise order.

You will be given a sequence of steps, performed by hero, each step described by a corresponding letter. You are to
tell after all these steps, how far the hero is now from his initial position.

We agree that the hero is always placed at the center of the cell and that distance between centers of two adjacent
cells (i.e. sharing a side) is `1.0`.

**Input data** will contain number of test-cases in the first line.  
Next lines will contain the sequence of steps (one sequence per line) as a string of letters.  
**Answer** should contain the distances between starting and ending point for each of sequences, separated by spaces
and with accuracy of `1e-7` at least.

Example:

    input data:
	3
	AABF
	FEDCBA
	BCB
	
	answer:
	3.0 0.0 2.64575131