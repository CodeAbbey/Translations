<!-- #Point to Segment Distance -->

<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="150">
	<line x1="105" y1="1" x2="595" y2="149" stroke="#80FF80" stroke-width="1"/>
	<g stroke="#808080" stroke-width="1">
		<line x1="70" y1="60" x2="200" y2="30"/>
		<line x1="630" y1="20" x2="500" y2="120"/>
		<line x1="300" y1="40" x2="295" y2="58"/>
		<line x1="420" y1="140" x2="431" y2="101"/>
	</g>
	<line x1="200" y1="30" x2="500" y2="120" stroke="blue" stroke-width="3"/>
	<g stroke="none" fill="red">
		<circle cx="70" cy="60" r="3"/>
		<circle cx="300" cy="40" r="3"/>
		<circle cx="420" cy="140" r="3"/>
		<circle cx="630" cy="20" r="3"/>
	</g>
</svg>
</div>

Very common problem in computational geometry is to find distance between the **point** and the **line segment**. It is
heavily exploited in programming 3D video games when recalculating visibility of walls for player while redrawing
each frame (i.e it is could be solved for `1000` wall fragments in each frame and about `50` frames are completely
recalculated during each second).

The definition of the **distance between point and segment** is like following:

- draw a line through both ends of a segment (i.e. the line to which this segment belongs);
- from our point cast a perpendicular to this line - the length of this perpendicular is **the distance between
    the point and the line**;
- if the other end of the perpendicular belongs to our segment (i.e. lays between its ends), then the distance to this
    segment equals to distance to this line;
- otherwise distance from point to segment equals to distance to nearest of its ends.

For example, see the picture above - line segment is drawn with blue and perpendiculars from `2nd` and `3rd` points
fall directly onto this segment, so they represent the distance from these points. On other hand perpendiculars from
`1st` and `4th` points fall out of segment (and they are not shown), so that distances are defined simply by the
nearest end of a segment (*distances from all points are represented with grey lines*). The line on which the segment
lays is shown with light-green.

**Input data** will contain the number of test-cases in first line.  
The following lines contain six values each: `x1 y1 x2 y2 xp yp` - denoting the segment between points `(x1,y1)` and
`(x2,y2)` and the point `(xp,yp)` to which a distance should be calculated.  
**Answer** should contain distances from points to segments for each test-case, separated with spaces.

Example:

    input data:
	3
	1 1 5 5 2 3
	2 3 7 8 2 0
	12 8 18 3 5 7
	
	answer:
	0.707106781 3 7.07106781187

*Note that in the second test-case the shortest distance from point is to the end of a segment, not to a line to which
the segment belongs.*

Please, provide answers with accuracy of `1e-7` or better.
