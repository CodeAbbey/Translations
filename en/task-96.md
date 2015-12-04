*Thanks to [Nicolas Patrois](../user_profile/nicolaspatrois) for help in testing this problem!*

The [Snake](http://en.wikipedia.org/wiki/Snake_(video_game)) game is known since `1970-s`: the snake is creeping
through the field, eating food and avoiding collisions with itself and with borders.

In this problem you are to write program which simulates this game. You will be given the initial field setup and the
chain of moves performed by the snake.

You should determine at which step and which point the snake will collide with itself.

The field will be given in the following form:

	X X X - - - - - $ - - - - - $ - - $ $ - -
	$ - - - - - - - - $ - - $ $ - - $ - $ - -
	$ - - $ - $ $ - - - - - - - $ - - - - - -
	- $ - - $ - - $ - - - - - $ $ $ $ $ - $ $
	$ - - - $ $ - - - - - - - - - - - $ - - -
	- $ $ - - - - - - - - - - - - $ - - - - $
	$ - - - - - - - - $ - - - - - $ $ - - - -
	$ - - - $ - - $ $ - - - $ - $ $ - - - - -
	- - - - $ $ - - - - - - $ $ - - - - - - $
	- $ - - - $ - - - - - - - $ - - - - $ - $
	- - - - - $ - $ - - - - - $ $ - - - - - -
	- - - - - $ - - $ - - $ - - - - - - - - $
	- - $ - - $ - - - - - - $ - - - $ - - $ -

It will always be of the `21 x 13` size and the snake will always have the size `3` and will start from the top-left
corner, moving initially to the right.

The sequence of moves will look like:

	12 D 4 L 10 U 1 R 6 D 7 R 9 U 9 L 16

this should be read as:

- make `12` steps (advance 1 cell each time);
- turn "head" `down` (without making step);
- make `4` steps more;
- turn `left`;
- make `10` steps;
- turn `up`;
- make `1` step;
- turn `right`;
- make `6` steps;
- and so on...

With each step the snake moves its head to the adjacent cell according to current direction, and then draws its tail
from its last position (so after the `1-st` step the cell `(0,0)` becomes empty etc.) **Note** that the "turn of the
head" does not make a step - it does not change the length or position of the snake, it is an "imaginary" operation
(though if we print the head cell differently according to where the snake is looking to - we'll see the change).

However, if at the current step the snake advances to the cell containing the food (marked with `$` sign) it does not
remove its "tail" from the last cell so that its length is increased by `1` (since the "head" moves anyway).

**input data** will contain `13` lines depicting `21` cells each with marks `-` for empty cells, `$` for food and
`X` for cells occupied with snake.  
Next line will contain the sequence of steps as described above (numbers and letters `U`, `D`, `L`, `R`).  
**Answer** should contain `X` and `Y` coordinates of the cell where snake collides with itself and then `N` - the
number of steps befor collision occured.

**Notes**

- the snake will never hit the border, you need not check this;
- coordinates start from `0` and the origin is in the top left corner (as usual in computer graphics);
- the chain of moves will contain several more elements even after snake collides with itself - and even can
    collide with itself once more - but you should register the first collision!

Example:

	
	input data:
	X X X - $ - - $ $ - $ $ $ - - - - - - - $
	- - - $ - - - - - - - $ - - - - - $ $ $ -
	$ $ $ - - - - - $ - - - - $ $ - - - - $ $
	- $ - - - - - - $ $ - - - $ - - $ - - - -
	- $ $ - - - - $ - - - $ - - - - - - - - -
	$ - - $ - - $ - - $ - $ - - - - - - - - -
	- - - - - $ - - - - - - $ - - - - $ - - $
	- - - - - $ $ - $ - - $ - - - - $ $ - - -
	- $ - - - - - $ - $ - $ - - - - - - $ - -
	- $ $ - $ - - - - - - - $ - - - $ - $ - $
	- - - - - - - - - - - - - - $ $ $ - - - -
	- - - $ - - - - - - - - - $ - - - $ - - $
	- - - - - - - - - $ - - - - - - $ $ $ - -
	5 D 1 L 1 U 1 L 3
	
	answer:
	6 0 8

In this example after the first `6` moves the picture will look like:

	- - - - X X X X $ - $ $ $ - - - - - - - $
	- - - $ - - - X - - - $ - - - - - $ $ $ -
	$ $ $ - - - - - $ - - - - $ $ - - - - $ $
	- $ - - - - - - $ $ - - - $ - - $ - - - -
	- $ $ - - - - $ - - - $ - - - - - - - - -
	$ - - $ - - $ - - $ - $ - - - - - - - - -
	- - - - - $ - - - - - - $ - - - - $ - - $
	- - - - - $ $ - $ - - $ - - - - $ $ - - -
	- $ - - - - - $ - $ - $ - - - - - - $ - -
	- $ $ - $ - - - - - - - $ - - - $ - $ - $
	- - - - - - - - - - - - - - $ $ $ - - - -
	- - - $ - - - - - - - - - $ - - - $ - - $
	- - - - - - - - - $ - - - - - - $ $ $ - -

You may see that the snake has eaten `2` units of food and now have length of `5`.
