<!-- Bezier curves -->

<div>
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
        version="1.1" width="950" height="200">
	
	<defs>
		<g id="main">
			<path d="M 0,180 L 90,0 L 180,120 L 270,60" stroke="#888888" fill="none"/>
			<g fill="red">
				<circle cx="0" cy="180" r="5"/>
				<circle cx="90" cy="0" r="5"/>
				<circle cx="180" cy="120" r="5"/>
				<circle cx="270" cy="60" r="5"/>
			</g>
		</g>
	</defs>
	
    <g transform="translate(10,15)">
		<use xlink:href="#main"/>
		<g fill="#c000c0">
			<circle cx="30" cy="120" r="3"/>
			<circle cx="120" cy="40" r="3"/>
			<circle cx="210" cy="100" r="3"/>
		</g>
	</g>
	
    <g transform="translate(310,15)">
		<use xlink:href="#main"/>
		<path d="M 30,120 L 120,40 L 210,100" stroke="blue" stroke-width="1" fill="none"/>
		<g fill="#c000c0">
			<circle cx="60" cy="93" r="3"/>
			<circle cx="150" cy="60" r="3"/>
		</g>
	</g>
	
    <g transform="translate(610,15)">
		<path d="M 0,180 C 90,0 180,120 270,60" stroke="#aaaaaa" stroke-width="2" fill="none"/>
		<use xlink:href="#main"/>
		<path d="M 30,120 L 120,40 L 210,100" stroke="blue" stroke-width="1" fill="none"/>
		<path d="M 60,93 L 150,60" stroke="green" stroke-width="1" fill="none"/>
		<g fill="#c000c0">
			<circle cx="90" cy="82" r="3"/>
		</g>
	</g>

</svg>
</div>

Bezier curves are shapes very popular in computer design. They could be found among instruments in almost any
image editor, including **Microsoft Paint** presented with any version of **Windows**.

Initially they were invented by engineers working on design of car bodies at automobile industry. Now we will try to
learn how to create such curves programmatically.

---

**Algorithm**

The curve is defined by starting, ending and several intermediate points. The example above have `4` points - i.e.
only `2` intermediate.

At first step we draw a **polyline** between these points, from starting via all intermediate in order to the ending
one. It is shown with thin grey line at the picture.

Now suppose we choose some parameter `alpha` in range `0 ... 1` and divide each segment of the polyline according
to it, i.e. in ratio:

    alpha : (1 - alpha)

For example, in the drawing above `alpha = 0.333`.

For polyline drawn between `N` points and consisting of `N - 1` segments we get `N - 1` new points - they are shown
as small purple dots at the leftmost picture.

Let us link these new points with new polyline, consisting of `N - 2` segments. It is shown as thin blue line at
the central and right-most pictures.

Then we can divide these new segments with the same ratio `alpha` once more. So we build a third polyline (shown in
green at the rightmost picture).

We will continue building polylines until we get the last one consisting of only one segment. When we divide it with
the ratio `alpha`, we get a single point.

This last point is the point of the Bezier Curve corresponding to parameter `alpha`.

The remaining is simple - just repeat these steps for different values of `alpha` - for example:

    alpha = 0.00, 0.01, 0.02, 0.03, ... , 0.98, 0.99, 1.00

So that for example with `101` value (from `0` to `1` with the step of `0.01`) we get the same amount of points,
placed closely enough to each other. Connecting them we get the smooth curve (thick grey line at the rightmost
picture).

Please refer to [wikipedia article](http://en.wikipedia.org/wiki/Bezier_curve) for more examples and animated demo.

---

**Input data** will contain the number of initial points `M` and the number `N` of values for parameter `alpha`.  
Next `M` lines will contain coordinates of one initial point each (`X` and `Y`).  
**Answer** should contain `N` pairs of coordinates (also `X` and `Y`) for all calculated points lying on the given
curve. Pairs and points in them should be separated simply by space. Coordinates should be rounded to nearest
integer (because when we do graphics coordinates of pixels are of course integer).

**Note:** the values for `alpha` should be calculated by dividing the range `0.0 ... 1.0` into `N - 1` equal steps.

Example:

    input data:
	4 10
	0 180
	90 0
	180 120
	270 60
	
	answer:
	0 180 30 130 60 99 90 82 120 76 150 75 180 78 210 79 240 74 270 60

**Additional Exercise** for your own amusement - try to draw the resulting curve by the points which you calculated
using graphical instruments of your favorite programming language. Or you can do this loading these points into
`Microsoft Excel` (`Openoffice Calc`) and drawing `XY` chart by them.
