In the [Safe Landing](./safe-landing) problem we learned how the rocket is controlled manually while landing.

Now you are in charge of the Moon base and one of your principal responsibilities is to guide landing of the approaching
ships. These ships have simple automated landing system, so on approach they:

- report their mass, height and speed to you;
- receive control settings for their landing system which you should calculate.

Their landing system works similarly to one described in previous task with the following changes:

- fuel burning rate could be adjusted every `1` second (instead of every `10` seconds when working manually);
- the system receives from you three parameters - free fall time `tf`, initial burning rate `rate0` and amount by
	which the rate is changed every second `drate` (either positive or negative).

So after receiving your response, ship continues flying towards the Moon without starting engines for `tf` seconds,
after this engines are turned on with burning rate of `rate0`. Further on, this rate is increased by `drate` after
each second elapsed.

Note that at any time burning rate is limited between `0` and `100` (kilograms per second) bounds. E.g. if `rate0` is
`90` and `drate` is `1` then `10` second after engines are engaged you reach the rate `100` and then continue with
this rate. Also, of course, after fuel is exhausted landing system have no influence on further flight and the ship is
again simply in free fall.

E.g. the CPU on board of the ship executes program similar to this:

		# input parameters: free_time, rate_initial, rate_change
		
		steps = 100
		dt = 1 / steps       # dt will be 0.01 seconds
		t = 0
		
		while (not_landed) :
            if t >= freeTime :
                rate = rate_initial + rate_change * (t - free_time)
				rate = min(max(rate, 0), 100)
            else :
				rate = 0
			end if
			
			for i = 0..99 :
			    perform_simulation_step(rate, dt)
			end for
			
			t = t + 1
		end while

You will receive requests from several ships at once - and you should provide them for settings which will allow them
to touch down with safe small speed.

So you need to solve a kind of minimization problem (search over parameters to minimize final speed) and there are
many ways. For example you may try [Gradient Descent](./gradient-descent-for-system-of-linear-equations) with proper
scaling of parameters or probably [Random Search](./random-search-optimization) approach.
Any of them may appear bit tricky because of the somewhat specific target function behavior, but some tuning should
help. You may even come up with some hybrid version - remember that your goal is to make algorithm fast: obviously it
will not do if the ship lands in `3` minutes and your algorithm can only find suitable parameters in twise this time :)

###Constant parameters

- Moon radius is `1737.1` km;
- gravity acceleration at its surface is `1.622` m/s^2;
- your rocket exhaust speed is `2800` m/s;
- simulation should be performed with smaller steps of `dt = 0.01` seconds;
- touch-down speed should not exceed `5` m/s.

###Input and Output

**Input data** contain the amount of ships sending request for landing to you (on the first line).  
Next lines give four values: `m` (mass of the ship itself), `mf` (mass of remaining fuel), `h` (current altitude),
`v` (current speed).  
**Answer** should return three values for each ship - `tf` (non-negative integer), `rate0` (between `0` and `100`)
and `drate` (either positive or negative) in the same order in which requests came.

Example:

    input data:
	2
	6500 7600 200000 1660
	5400 7200 210000 1700
	
	answer:
	60 69.21 0.000154384 73 85.18 -0.284587568
	
	
_For this example the first ship lands with the speed `v = 2.74 m/s` after `t = 160.22 sec`  
and the second one with the speed `v = 1.46 m/s` after `t = 159.01 sec`.  
This information is provided to you for debugging purpose._
