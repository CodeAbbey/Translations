<div class="centered">
<span class="hint">Optimized for use with Google Chrome<br/>Try to drag the ball with mouse...</span><br/>
<canvas id="demo" width="500" height="250" style="border:5px solid #888;border-radius: 5px;background: black;"></canvas>
<br/>
<input type="button" onclick="buttonReset()" value="Reset"/>
</div>

Extending the problem with [Flying Text Screensaver](./flying-text-screensaver) we switch from "console" or
alpha-numeric screen mode to graphics. So now we'll try to simulate the behavior of the billiard ball.

We are concerned about two laws of its movement:

- the ball should bounce from the borders;
- the speed should slowly decrease to zero.

Supposing that the simulation is performed in small steps (for example, `10ms` each) we can regard the rules
described below.

###Position and velocity

Initial position of the ball is described by its coordinates `X` and `Y`. Of course its radius `R` also is important
since the ball could not get to the border (of the table) closer than this radius allows. So if the table have
width `W` and height `H` then the ball's coordinates are always bounded:

    X in [R ... W - R)         Y in [R ... H - R)

Initial velocity of the ball could be described by its horizontal and vertical components `Vx` and `Vy`. Full velocity
is of course the hypotenuse of the triangle built upon these two sides:

    V = sqrt(Vx*Vx + Vy*Vy)
	Vx = V * cos(a)
	Vy = V * sin(a)

here `a` is the angle between `OX` axis and the vector of velocity.

At each step of the duration `dt` the position of the ball is changed according to its speed:

    X += Vx * dt
	Y += Vy * dt

###Bouncing

Since the borders of the table are parallel to coordinate axes it is very easy to provide bouncing. For example let us
study the bouncing from the upper horizontal border, i.e. line at the `Y=0` (we know that on the screen `Y` axis
is directed downwards, unlike in math).

Obviously the ball of the radius `R` could not have its `Y` position smaller than `R` in respect to this border. So if
after the step is calculated (as described above) and we found that new position has `Ynew < R` we should do two things:

- change the sign of vertical component of the speed (i.e. `Vy *= -1`);
- adjust the position of the ball as if it bounced from the line `Y = R` instead of crossing it.

The second is done by the following calculation:

    Ynew += 2 * (R - Ynew)

i.e. we check how much the ball have "trespassed" the border (`R-Y`) and compensate it twice - first to return to line
`Y=R` and then to "travel" the same distance at the opposite direction. Another way to write it is `Ynew = R + (R - Ynew)`.

###Slowing down

For the sake of simulation we can use some simple law of decreasing the speed. The simplest of course is to assume that
constant deceleration is applied to velocity each step:

    V -= A * dt

where `A` is the constant value of deceleration (negative acceleration).

It is not quite correct in the sense of physics, but it will work well and for the eye of user it looks OK enough.

###Problem statement

Your goal is by given parameters (initial position and velocity, table size and deceleration) to tell the final position
of the ball (where it came to rest). You may try to play with the demo above to understand the motion of the ball better.

The step of simulation `dt` is to be chosen by you. Make sure it is small enough to not affect the result accuracy.

**Input data** will contain the values `W`, `H`, `X`, `Y`, `R`, `Vx`, `Vy`, `A` - width and height of the table,
initial position, ball radius, components of the initial speed, deceleration constant.  
**Answer** should contain two values `X` and `Y` of the final position (rounded to the nearest integer).

Example:

    input data:
	500 250 50 50 10 86 86 5
	
	answer:
	136 176

In this case ball stops after `6` bounces from the following sides in order: `bottom`, `top`, `right`, `bottom`, `top`, `left`.

*Note that the problem could be solved with pure geometry instead of simulation with steps. However it is not
recommended since geometric approach could not be easily fitted to more complicated laws of motion (which we
are going to use in an advanced version of the problem).*

<script src="http://codeabbey.github.io/simple-pool/pool.js"></script>

<script>
function overrideSettings() {
    nBalls = 1;
    rad = 10;
    colors.ballFill = '#A0A0A0';
}
window.onload = function() {
	poolInit();
}
</script>
