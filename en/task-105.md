<div>
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
        version="1.1" width="950" height="170">
	
	<defs>
		<g id="main" fill="red">
			<circle cx="0" cy="100" r="5"/>
			<circle cx="60" cy="0" r="5"/>
			<circle cx="110" cy="20" r="5"/>
			<circle cx="150" cy="50" r="5"/>
			<circle cx="190" cy="110" r="5"/>
			<circle cx="120" cy="135" r="5"/>
			<circle cx="35" cy="150" r="5"/>
	    </g>
		<g id="back">
			<path fill="#eef" stroke="blue" stroke-width="2" d="M 0,100 L 60,0 110,20 150,50 190,110 120,135 35,150 z"/>
		</g>
	</defs>
	
	<g transform="translate(10,10)">
		<use xlink:href="#back"/>
		<path stroke="#aaa" fill="none" d="M 60,0 L 35,150 110,20 120,135 150,50"/>
		<use xlink:href="#main"/>
	</g>
	
	<g transform="translate(310,10)">
		<use xlink:href="#back"/>
		<path stroke="#aaa" fill="none" d="M 60,0 L 35,150 M 60,0 L 190,110 M 60,0 120,135 M 60,0 150,50"/>
		<use xlink:href="#main"/>
	</g>
	
	<g transform="translate(610,10)">
		<use xlink:href="#back"/>
		<path stroke="#aaa" fill="none" d="M 60,0 L 95,80 110,20 M 0,100 L 95,80 150,50 M 190,110 L 95,80 120,135 M 95,80 L 35,150"/>
		<use xlink:href="#main"/>
	</g>
</svg>
</div>

You have probably already wrote the program for calculating [Area of Triangle](./triangle-area) - let us now get
acquainted with the extention of this problem - the calculation of area for arbitrary convex polygon.

Polygon is called **convex** if each of its angles is less than `PI/2`, or in other words, if any line connecting any
pair of points belonging to it lies completely inside. This somewhat simplifies handling of such shapes.

You need to reduce this problem to one with triangles. We hope that pictures above may give you idea on three
different approaches to do this.

**Input data** contain the number of vertices of the polygon.  
Next lines contain a pair of numbers each - `X` and `Y` coordinates for the vertex (in correct CCW order).  
**Answer** should contain the area of the shape surrounded by these points.

Example:

    input data:
	5
	51 9
	77 10
	92 71
	62 84
	29 94
	
	answer:
	3274.5
