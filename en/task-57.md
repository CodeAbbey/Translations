<div class="text-center">
	<img alt="smooth line chart example" src="http://s5.postimg.org/69l1zxd4n/smooth_weather.png"/>
</div>

Little Merlin wants to become a meteorologist. He measures the temperature of the air each hour so that after
several days he has a long sequence of values.

However, his instruments are not ideal so the measurements are not exact - they randomly jump up and down by several
degrees from the real values.

Observing this, Merlin decided to make his data more smooth. To achieve this he only needs every value to be
substituted by the average of it and its two neighbors. For example, if he have the sequence of `5` values like this:

    3 5 6 4 5

Then the second (i.e. `5`) should be substituted by `(3 + 5 + 6) / 3 = 4.66666666667`,  
the third (i.e. `6`) should be substituted by `(5 + 6 + 4) / 3 = 5`,  
the fourth (i.e. `4`) should be substituted by `(6 + 4 + 5) / 3 = 5`.  
By agreement, the first and the last values will remain unchanged.

At the picture above the blue line shows unprocessed data while red represents the smoothing.

You are to write the program which helps Little Merlin in this whimsical algorithm of digital signal processing.

**Input data** will contain the length of the sequence in the first line.  
The second line will contain the measurements itself.  
**Answer** should contain the processed sequence. All values should be calculated to precision of `1e-7` or better.

Example:

    input data:
	7
	32.6 31.2 35.2 37.4 44.9 42.1 44.1
	
	answer:
	32.6 33 34.6 39.1666666667 41.4666666667 43.7 44.1

