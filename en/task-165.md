<div class="centered">
	<div class="strong hint">Play live demo to get acquainted with the physics of the rocket landing!</div>
	<div class="strong hint">Try to land with the speed less than 10 m/s.</div>
	<div style="display:inline-block;border: 5px solid #555; border-radius: 5px;">
		<div id="terminal"></div>
	</div>
</div>

In the year of `1969` first ever people from the Earth landed on the Moon. As **Neil Armstrong** the commander of the
[Apollo 11](http://en.wikipedia.org/wiki/Apollo_11#Lunar_descent) mission told about it _one small step for man,
one giant leap for mankind!_ However we rarely think about how technically complicated this task was.

Here is a pilot's landing simulator - imagine, you are being trained for next manned missions to the moon. I have found
the game in the old book [101 BASIC Computer Games](http://en.wikipedia.org/wiki/BASIC_Computer_Games) and so here is
an exercise based on it.

###Problem statement

You are in the space craft which is approaching the Moon. Initially you flight (or rather fall) to the surface with the
great speed. However you have some fuel for landing and you can burn it in the retrorockets for "braking".

You can change the settings of the engine each `10` seconds. For each next period you specify the burning rate of the
fuel - i.e. how many kilograms of fuel should be fed to the engine each second.

Try playing the demo above. You will see that burn rate could be set to any value between `0` and `100`. When engines
are off you are free falling - and you will see that:

- height is decreased according to descent speed 
	i.e. with speed `300 m/s` you travel roughly `3000 m` in `10 sec` period;
- speed itself is increading according to gravity acceleration
	i.e. with gravity `1.5 m/s^2` the speed increases from `300` to about `315` after ten seconds;
- gravity itself is slightly increasing as you approach the surface.

If you turn on engines (i.e. set non-zero burning rate), the speed is also affected by retro-rockets according to
Tsiolkovsky Rocket Equation.

You can find detailed explanations of these calculations in the
[article on rocket flight and gravity](../wiki/rocket-equation-and-gravity).

You will be given a sequence of values - successive settings of burning rate for each `10` seconds of the flight. Your
goal is to tell the speed the craft will have on touch down (i.e. on reaching the height `0`). Perform simulation with
small steps, for example `dt=0.1 sec`.

Additional data you will need:

- Moon radius is `1737.1 km`;
- gravity acceleration at its surface is `1.622 m/s^2`;
- your rocket exhaust speed is `2800 m/s`.

**Input data** will have the mass of the craft, mass of the fuel, initial height and descent velocity in the first line.  
Next line will specify several values - settings of the burn rate for each next period. After the fuel is ended the
further settings should be ignored. If after proceeding through all the sequence the rocket still is not on the
surface, continue calculation as it is in free fall.  
**Answer** should give single value - the speed on reaching the Moon surface. Error about `1%` is acceptable.

Example #1:

    input data:
	7500 7500 200000 1600
	0 0 0 0 0 0 0
	
	answer:
	1772

Example #2:

    input data:
	6000 7000 150000 2000
	0 100 100 100 50 50 50 50 50 50 100 100 100
	
	answer:
	273

<script src="http://codeabbey.github.io/safe-landing/jsmonoterm.js"></script>
<script src="http://codeabbey.github.io/safe-landing/rocket.js"></script>
