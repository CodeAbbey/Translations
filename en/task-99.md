<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="520px" height="300px" style="margin-left:240px">
	<rect x="0" y="0" width="520" height="300" stroke="#aaaaaa" stroke-width="2" fill="#dddddd"/>
	<g transform="translate(10,-10)">
	    <path d="M 0,300 h100 v-20 h60 v-20 h20 v-20 h40 v-20 h20 v-20 h60 v-20 h100 v-20 h20 v-20 h60 v-20 h20" stroke="blue" stroke-width="2" fill="none"/>
		<path d="M 0,300 22,274 45,250 67,228 90,208 112,190 135,174 157,160 180,148 202,138 225,130 247,124 270,120 292,117 315,117 337,119 360,122 382,128 405,135 427,145" stroke="red" stroke-width="2" fill="none"/>
	</g>
</svg>
</div>

What reasons underlay the creation of the very first computers? It is not a secret that there were military interests.

The art of war yields many interesting problems in math, physics, logic etc. The calculations for ballistics are among
them. Let us try to solve a simple task in this field.

The CodeAbbey is building the tank (i.e. armoured vehicle) able of firing the laughter - the main goal is to create the
weapon of the peace. Now we are engaged in testing the prototype.

Today brethren conduct the experiments with shooting up the hill. The tank is brought before the ascending slope
and shoots the bomb of joy against it.

We can measure both the initial velocity of the projectile and the angle of shooting. All we want to calculate is where
the bomb should hit the slope - to check whether the real trajectory is similar to ideal one.

**Technical details**

Our tank is quite small, almost micro-tank, so you can safely assume that the trajectory starts from the point `(0, 0)`.

The shooting range is `160` metres long and the slope is built of the large cubes having the side of `4` metres. So the
profile of the slope is given by `40` integers, specifying the height of the pillar of the blocks, for example:

    0 0 1 1 1 2 2
	
describes the slope of the following form:

					                        X X X X X X X X  8
					                        X X X X X X X X
					                        X X X X X X X X
					                        X X X X X X X X
					X X X X X X X X X X X X X X X X X X X X  4
                    X X X X X X X X X X X X X X X X X X X X 
                    X X X X X X X X X X X X X X X X X X X X 
                    X X X X X X X X X X X X X X X X X X X X 
	- - - - - - - - - - - - - - - - - - - - - - - - - - - -  0
	0       4       8       12      16      20      24

You see that up to distance of `8` metres there are no blocks, then from mark `8` to `20` there are lying three
blocks and in two next positions (from `20` and from `24`) there are two stacks of two blocks.

The slope is never descending, so that integers in array will be in increasing order.

The acceleration due to gravitation is exactly `9.81 m / s^2` and the drag (the mechanical resistance of the air)
should not be taken into consideration.

Tank is tested against `3` slopes and performs `3` shot at each.

**Input data** will contain three blocks.  
Each block starts from the line of `40` integers describing the slope profile.  
Then three lines follow describing three shots made - each contains `V` - initial velocity (`m / s`) and the angle
of elevation of the barrel `A` expressed in degrees.  
**Answer** should contain `9` integers - the distance at which the bomb hits the slope, rounded down.

Example:

	input data:
    0 0 0 0 0 1 1 1 1 2 2 2 2 2 2 3 4 5 6 6 7 8 9 9 10 10 10 10 10 10 11 11 12 13 14 15 16 16 17 18
	42 42
	34 33
	41 52
	0 0 0 0 0 1 1 1 2 3 3 4 5 5 5 6 7 8 9 9 9 9 9 9 9 10 11 11 12 13 13 13 13 13 14 15 15 15 15 16
	30 47
	36 55
	43 62
	0 0 0 0 0 0 1 1 1 1 2 3 3 3 3 3 4 5 5 6 7 7 8 8 8 9 9 10 11 12 13 13 13 13 14 14 15 16 16 17
	42 37
	37 32
	32 52
	
	answer:
	96 68 120 60 88 120 97 68 76