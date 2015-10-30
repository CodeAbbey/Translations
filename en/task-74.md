<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="190">

<g fill="none" transform="translate(250, 95)">
	<circle cx="0" cy="0" r="90" stroke="black" stroke-width="3"/>
	<g stroke-width="2" stroke="black">
		<circle cx="0" cy="-80" r="5"/>
		<circle cx="40" cy="-70" r="2"/>
		<circle cx="70" cy="-40" r="2"/>
		<circle cx="80" cy="0" r="2"/>
		<circle cx="70" cy="40" r="2"/>
		<circle cx="40" cy="70" r="2"/>
		<circle cx="0" cy="80" r="2"/>
		<circle cx="-40" cy="-70" r="2"/>
		<circle cx="-70" cy="-40" r="2"/>
		<circle cx="-80" cy="0" r="2"/>
		<circle cx="-70" cy="40" r="2"/>
		<circle cx="-40" cy="70" r="2"/>
	</g>
	<path d="M 0,-15 L 0,70" stroke="blue" stroke-width="3"/>
	<path d="M 12,3 L -48,-12" stroke="blue" stroke-width="6"/>
</g>

</svg>
</div>

The face of analog clock has two hands and is proportionally divided by `12` marks. The shorter `hour hand` makes
the whole turn (`360` degrees) in `12` hours, while the longer `minute hand` makes the whole circle each hour.
See [Clock Face](http://en.wikipedia.org/wiki/Clock_face) on wiki for more details.

Suppose, the [Cartesian Coordinate System](http://en.wikipedia.org/wiki/Cartesian_coordinate_system) (i.e. ordinary
rectangular coordinate grid) is placed upon the clock face so that the center of the face has coordinates `10, 10` and
`Y` axis is directed upwards while `X` axis is directed to the right (i.e. at `3:00` minute hand is parallel to `Y`
axis and hour hand is parallel to `X` axis).

Assuming the length of the minute hand be `9` and the length of the hour hand be `6` you are to find coordinates of
the hand ends for each given time - e.g. `(16 10)` and `(10 19)` for the time `3:00`.

**Input data** contain the number of test cases.  
Following line contains the testcases themselves in form `3:15`, `21:44` etc.  
**Answer** should contain four real numbers for each test case - `X` and `Y` coordinates for `hour` hand, then `X` and
`Y` coordinate for minute hand. All values should be simply separated with spaces.

*Real values should have accuracy of `1e-7` or better. Time is specified as a value from `0:00` to `23:59`.*

Example:

    input data:
	3
	12:00 15:00 9:30
	
	answer:
	10.0 16.0 10.0 19.0 16.0 10.0 10.0 19.0 4.20444504 11.55291427 10.0 1.0