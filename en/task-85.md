<div>
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
        version="1.1" width="950" height="160">
	<g fill="none" transform="translate(60,30)">
		<path d="M 20,20 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#ff4444"/>
		<path d="M 100,20 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#6666ff"/>
		<path d="M 20,100 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#22ff22"/>
		<path d="M 100,100 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#dddd00"/>
		<path d="M 60,4 l 0,120 M 0,64 l 120,0" stroke="grey"/>
		<path d="M 0,44 A 75,75 0,0,0 0,84 m -4,-5 l 4,5 3,-5" stroke="#ff88ff"/>
		<path d="M 120,84 A 75,75 0,0,0 120,44 m -3,5 l 3,-5 4,5" stroke="#ff88ff"/>
	</g>
	<g fill="none" transform="translate(260,30)">
		<path d="M 60,4 l 0,120 M 0,64 l 120,0" stroke="grey"/>
		<path d="M 4,60 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#ff4444"/>
		<path d="M 60,3 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#6666ff"/>
		<path d="M 60,117 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#22ff22"/>
		<path d="M 117,60 l 2,8 -6,-5 8,0 -6,5 2,-8" stroke="#dddd00"/>
	</g>
</svg>
</div>

Let's practice the geometry programming of rotations. Such functionality is quite popular in graphic editors, but it
is not the only use.

For example here is the widget [Sphere Tag Cloud](http://jstagsphere.sourceforge.net/) which can be used in creating
funny design of the web-page. Dragging the mouse over the cloud you should see it scrolling like a globe. The effect
is achieved by performing just two rotations around two axes (for each of floating element).

We'll start with something simpler. Suggest we have a planar map with points on it. For example it could be the
picture of a sky with stars shining.

The task is to perform rotation of the map by the given angle. Round the resulting coordinates to nearest integer.

To check the result please output the names of stars
sorted by `Y` coordinate and then by `X` (if the `Y`s are equal).

**Input data** contain the number of stars `N` and the rotation angle `A`
(counterclockwise, from `0` to `360` degrees).  
Next lines will contain data about one star each in form `Name X Y`. Coordnates would be integer, not exceeding `1000`
in absolute value.  
**Answer** should give the names of stars sorted by `Y` and then by `X` after rotation (and rounding).

**Note:** sorting should be performed in ascending order, i.e. from smallest values to largest.

Example:

    input data:
	4 45
	Deneb -10 10
	Algol 10 10
	Sirius -10 -10
	Mira 10 -10
	
	answer:
	Sirius Deneb Mira Algol

*You may see schematic diagram of such rotation on the picture above. Here Sirius is green, Deneb is red, Mira is
yellow and Algol is blue.*