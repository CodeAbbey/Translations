<div class="text-center">
	<a href="http://en.wikipedia.org/wiki/File:Animation_showing_movement_of_2003_UB313-2-.gif">
		<img src="http://s24.postimg.org/lltoa4el1/Animation_showing_movement_of_2003_UB313_2.gif"
			alt="Discovery of Eris by photos" width="400px" height="400px"/>
	</a>
	<div class="hint">Dwarf-planet <a href="http://en.wikipedia.org/wiki/Eris_(dwarf_planet)">Eris</a>
		was discovered by its movement on the sky</div>
		<br/>
</div>

Monks of CodeAbbey are going to create their own observatory, to perform researches in astronomy - and
besides others - "hunting" for comets and asteroids. Nowadays, such buisiness requires not only good telescope and
clean sky, but also two important things:

- some photo-device attached to telescope, to make shots of interesting parts of the sky;
- whimsical software to process these shots later.

For example, look at the animation above. It shows three shots with which the dwarf-planet Eris was discovered
back in 2005. Look at the point of "arrow" formed by two yellow lines - close to it small speck of light is moving.

_Do you know what Eris is? It is a planet has the size larger than Pluto - the fact due to which the latter had
eventually lost its title of the `9-th` planet of the Solar System.'

You can guess how hard it was to analyze such images without a computer:

- several shots should be made targeting at almost the same point in the sky;
- their brightness could depend on weather conditions and other factors;
- resulting pictures will anyway be slightly shifted and rotated.

###Problem Statement

Suppose that some preliminary image preprocessing was already done and you have data in form of
coordinates of stars on two pictures. These pictures are about `100x100` millimeters, and coordinates are
also given in millimeters relative to their center. Look at the schematic reprsentation below:

<div class="text-center">
	<a href="http://s22.postimg.org/jpfqen26p/ca_204.png" title="click to view full-size" target="_blank">
		<img src="http://s22.postimg.org/jpfqen26p/ca_204.png"
			alt="Two schematic images of the part of star field" width="800px" height="360px"/>
	</a>
</div>

You see that in both pictures stars are shown in roughly circular area (think of it as of apperture of our telescope),
and you can find out that they represent the same piece of the sky - thoulgh slightly rotated and slightly shifted.

You also can see that one of the stars (marked with red arrows) have changed its position relative to others.

Your task is to find out such a "wandering star" for it could be comet or asteroid with high probability.

<div>
<div class="attention">Note that some stars which are close to the edge could be absent from one
of pictures (due to shift) - but the "wandering star" is not that far from the center and therefore
is presented on both of images.</div>
<br/>
</div>

**Input data** contains two sections corresponding to two images.  
Each sequence starts with a single integer - amount of stars listed.  
Then the coordinates (`X` and `Y`) of stars follow.  
**Answer** should give two indexes (`0`-based) of the wandering star in the first and second section respectively.

_The example is the same as pictures above. The star `#29` from the first section
with coordinates `(-18.2, 11.1)` is the same as the star `#3` from the second section
with coordinates `(-19.7, 6.9)`._

Example:
	
	input data:
	94						# section 1 contains 94 stars
	-47.5 -10.4
	19.1 25.9
	18.9 -10.4
	-2.1 -47.6
	41.8 -12.1
	-15.7 12.1
	-11.0 -0.6
	-15.6 -7.6
	14.9 43.5
	16.6 0.1
	3.6 -33.5
	-14.2 20.8
	17.8 -29.8
	-2.2 -12.8
	44.6 19.7
	17.9 -41.3
	24.6 37.0
	43.9 14.5
	23.8 19.6
	-4.2 -40.5
	32.0 17.2
	22.6 -26.9
	9.9 -33.4
	-13.6 6.6
	48.5 -3.5
	-9.9 -39.9
	-28.2 20.7
	7.1 15.5
	-36.2 -29.9
	-18.2 11.1
	-1.2 -13.7
	9.3 9.3
	39.2 15.8
	-5.2 -16.2
	-34.9 5.0
	-13.4 -31.8
	24.7 -29.1
	1.4 24.0
	-24.4 18.0
	11.9 -29.1
	36.3 18.6
	30.3 38.4
	4.8 -20.5
	-46.8 12.1
	-44.2 -6.0
	-1.4 -39.7
	-1.0 -13.7
	13.3 23.6
	37.4 -7.0
	-22.3 37.8
	17.6 -3.3
	35.0 -9.1
	-44.5 13.1
	-5.1 19.7
	-12.1 1.7
	-30.9 -1.9
	-19.4 -15.0
	10.8 31.9
	19.7 3.1
	29.9 -16.6
	31.7 -26.8
	38.1 30.2
	3.5 25.1
	-14.8 19.6
	2.1 29.0
	-9.6 -32.9
	24.8 4.9
	-2.2 -24.7
	-4.3 -37.4
	-3.0 37.4
	-34.0 -21.2
	-18.4 34.6
	9.3 -45.2
	-21.1 -10.3
	-19.8 29.1
	31.3 37.7
	27.2 19.3
	-1.6 -45.6
	35.3 -23.5
	-39.9 -19.8
	-3.8 40.6
	-15.7 12.5
	-0.8 -16.3
	-5.1 13.1
	-13.8 -25.7
	43.8 5.6
	9.2 38.6
	42.2 0.2
	-10.0 -48.6
	14.1 -6.5
	34.6 -26.8
	11.1 -6.7
	-6.1 25.1
	-38.3 8.1
	92						# section 2 contains 92 stars
	-14.8 10.9
	18.8 -0.1
	-11.3 5.7
	-19.7 6.9
	-11.5 -16.7
	-45.4 -15.3
	6.0 -46.9
	-24.1 -26.3
	30.2 27.4
	21.4 -27.2
	12.1 -36.1
	23.8 -38.7
	41.5 5.3
	-8.7 25.5
	36.6 -5.9
	43.7 -14.6
	-9.7 -8.6
	34.7 -19.3
	-15.5 19.3
	21.4 3.9
	34.0 29.8
	6.5 19.5
	28.2 -21.7
	13.4 -41.8
	-25.9 -6.9
	37.5 27.8
	18.1 44.7
	-43.0 -19.9
	-15.7 18.0
	2.4 -31.6
	9.6 -37.6
	15.4 -28.8
	43.6 -11.2
	4.6 -10.2
	-8.8 38.2
	8.7 -34.6
	-4.7 14.1
	-1.7 31.3
	0.6 27.9
	26.3 13.7
	-1.2 26.3
	32.1 -17.7
	15.5 32.6
	-14.4 -12.6
	22.3 -22.5
	7.0 48.5
	-6.4 20.5
	-42.9 4.2
	-23.0 31.6
	-24.6 14.0
	-30.2 -26.5
	-29.0 15.7
	6.0 36.3
	44.3 13.5
	-27.6 33.7
	13.4 -43.9
	10.5 28.9
	47.0 1.4
	10.2 14.0
	13.3 -15.9
	-3.4 -25.6
	-14.7 10.5
	21.6 27.6
	21.8 10.6
	-37.8 -14.2
	7.6 -21.8
	-8.6 1.3
	6.8 -13.3
	40.9 -15.3
	-10.3 41.1
	6.0 -10.8
	-1.5 -31.4
	-35.6 1.0
	2.5 -14.3
	24.4 -2.6
	-24.1 -35.3
	-29.9 -34.7
	15.9 -1.0
	19.5 7.0
	44.5 19.1
	39.7 2.7
	2.7 42.4
	-23.0 25.9
	25.0 28.2
	31.2 -32.8
	3.9 -38.4
	-44.8 2.7
	-39.9 -19.3
	-7.0 -0.6
	5.8 -10.9
	-44.5 19.9
	-31.5 -1.2
	
	answer:
	29 3

