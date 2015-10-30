<!-- #Fahrenheit to Celsius -->
This programming exercise is roughly the same as counting sums in loop, but it needs bit more calculations.

<div class="text-center">
	<img alt="fahrenheit and celsius" src="http://s5.postimg.org/3tpo5bg6v/fahrenheit.png"/>
</div>

*Note: the problem [Rounding](./rounding) explains the rounding algorithm which is used in this task.*

There are two widespread systems of measuring temperature - Celsius and Fahrenheit. First is quite popular in Europe
and second is well in use in United States for example.

By Celsius scale water freezes at 0 degrees and boils at 100 degrees. By Fahrenheit water freezes
at 32 degrees and boils at 212 degrees. You may learn more from [wikipedia on Fahrenheit][wiki]. Use these two points
for conversion of other temperatures.

[wiki]: http://en.wikipedia.org/wiki/Fahrenheit

You are to write program to convert degrees of Fahrenheit to Celsius.

**Input data** contains `N+1` values, first of them is `N` itself (**Note** that you should not try to convert it).  
**Answer** should contain exactly `N` results, rounded to nearest integer and separated by spaces.

Example:

    data:
    5 495 353 168 -39 22
    answer:
    257 178 76 -39 -6

*Please note that first `5` is not a temperature, but the amount of values to convert!*