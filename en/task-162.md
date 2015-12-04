_Thanks a lot to [Sergey Pobezhimov](../user_profile/moffserge) and [Nicolas Patrois](../user_profile/nicolaspatrois)
for proposing this task and providing valuable hints on implementation!_

<div class="centered hint">
	<img alt="Rubik's cube rotations for notation" src="http://s30.postimg.org/v89nmmbu9/3x3_Notation.jpg"/><br/>
	<span>All operations with 3x3 cube could be described using only 6 letters!</span>
</div>

Probably there is no one who hadn't heard of this fascinating puzzle -
[Rubik's Cube](http://en.wikipedia.org/wiki/Rubik%27s_Cube). I cracked it finally only about the age of 30 - playing
with the toy for two weeks while traveling to work and back by subway. I found several sequences of moves (people
call them "algorithms") which exchange positions of only few elements leaving others untouched - after that the puzzle
becomes easier...

Your task will be simpler - given a sequence of rotations you are to track changes of positions of some elements.

To describe the rotations the simple system is used. Suppose for example, we hold the cube (in its initial setup) so
that the `yellow` side is turned to us while `red` is looking up. We now can name all `6` sides with letters:
`F` (front), `B` (back), `L` (left), `R` (right), `U` (upper), `D` (down).

Now let us agree that each move is performed by rotating the chosen side **clockwise**, e.g. `F` means we turn front
side, so that three elements with yellow and red stickers travel to the right. See the arrows at the picture above
for better understanding.

Any transformations of the cube could be described with only these `6` kinds of moves (probably even less will do).

Now imagine that the stickers on the front side (here they are yellow) are numbered in the following manner:

    7 8 9
	4 5 6
	1 2 3

So that `9` is the corner element with red, yellow and blue stickers, while `8` is edge element with red and yellow ones.

To answer this exercise you should tell **to which side** each of these numbered stickers goes after a series of moves.
For example after `R` and `F` moves the numbers `1`, `2`, `4`, `5`, `7`, `8` will remain at front side, while `6` and
`9` turn to upper side and `3` is found on the right side.

**Input data** will give the total number of moves in the first line.  
Next line will contain sequence of moves as space-separated letters.  
**Answer** should contain `9` letters describing sides on which each of the numbered stickers will land at last.

Example:

    input data:
	5
	L U F B B
	
	answer:
	U F F D F F L L U
