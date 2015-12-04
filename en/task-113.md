*In the year of 2009 small company where I was working as a junior electronics developer was offered to produce a
whimsical solution for military forces. One of the parts of the problem was about geometry.*

Here is the "polygon" - the place where artillery men perform their training. Let it have square form of `10x10`
kilometres.

Several seismic sensors are planted at the different points of this place. We know their coordinates exactly (they
have built-in GPS).

With this sensors it is possible to register the timestamp of all shell explosions occuring at the polygon.

Since there is usually some distance between explosion point (let call it **ground zero**) and each of sensors, the
timestamp registered by them is slighthly behind the time of the explosion itself. We assume that the "shake" of the
ground travels (or propagates) with the constant (but unknown) speed through the soil.

For example if the seismic wave made by the shell occured at `12:00:00.000` time and the speed of propagation is
`1000 m/s` then the sensor at `2.5km` distance will register it at `12:00:02.500`.

My task was to determine the locations and times of explosions by the records from seismic sensors. Now it becomes
your task, though in simplified form :)

**Input data** contain the number of test-cases in the first line.  
Next lines will describe one test-case each.  
Every test-case contains the number of sensors at first and then triplets of values `X`, `Y`, `T` for each of
sensors. `X` and `Y` are coordinates of the sensor, they will be integers in range `0...10000`, and `T` is the
timestamp of the event as registered by this sensor (float value in seconds). Please, round coordinates to nearest
integer and seconds to one digit after decimal point (also to nearest). Triplets in input are separated with
semicolons.  
**Answer** should contain a triplet of values - coordinates and the timestamp of the explosion itself -
for each of test-cases (in form `X Y T` also). Use only spaces as separators here.

*Note that the speed of propagation of the seismic wave is not necessarily the same for different test-cases.*

Example:

    3
	4; 303 6874 69.957781641; 1772 9314 73.479878657; 7946 6024 78.055985299; 8812 157 82.230678694
	4; 119 7195 26.515150291; 5122 1579 28.920160546; 8633 7279 27.820585213; 5727 9281 25.468806669
	4; 640 7585 102.002652597; 6350 369 102.650468713; 7244 3422 99.254436796; 5967 5190 96.279961865
	
	1319 5468 67.1 3839 7135 22.0 5348 5789 95.1
	