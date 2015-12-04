<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="100">

<g stroke="black" stroke-width="3" fill="none">
    <rect x="10" y="10" width="80" height="80" rx="10" ry="10"/>
    <rect x="110" y="10" width="80" height="80" rx="10" ry="10"/>
    <rect x="210" y="10" width="80" height="80" rx="10" ry="10"/>
    <rect x="310" y="10" width="80" height="80" rx="10" ry="10"/>
    <rect x="410" y="10" width="80" height="80" rx="10" ry="10"/>
</g>

<g fill="blue">
    <circle cx="30" cy="30" r="8"/>
    <circle cx="70" cy="70" r="8"/>
	
    <circle cx="130" cy="30" r="8"/>
    <circle cx="170" cy="70" r="8"/>
    <circle cx="130" cy="70" r="8"/>
    <circle cx="170" cy="30" r="8"/>
	
    <circle cx="330" cy="30" r="8"/>
    <circle cx="370" cy="70" r="8"/>
    <circle cx="330" cy="70" r="8"/>
    <circle cx="370" cy="30" r="8"/>
</g>

<g fill="red">
    <circle cx="230" cy="30" r="8"/>
    <circle cx="270" cy="70" r="8"/>
    <circle cx="250" cy="50" r="8"/>
    <circle cx="230" cy="70" r="8"/>
    <circle cx="270" cy="30" r="8"/>
	
    <circle cx="430" cy="30" r="8"/>
    <circle cx="470" cy="70" r="8"/>
    <circle cx="450" cy="50" r="8"/>
</g>
</svg>
</div>

Dice game of **Yacht** is played with `5` standard dice (having from `1` to `6` points on their sides). The player's
goal is to gather some beautiful combination of points. Suppose, the following combinations are respected:

- two of dice have the same points, like `3 6 5 6 1` - called **pair**;
- three of dice have the same points, like `2 4 5 4 4` - called **three**;
- four of dice have the same points, like `1 4 1 1 1` - called **four**;
- all five dice have the same points, like `2 2 2 2 2` - called **yacht**;
- two **pairs** at once, like `3 6 5 3 5` - called **two-pairs**;
- **pair** and **three** at once, like `1 6 6 1 6` - called **full-house**;
- sequence from `1` to `5`, like `2 4 3 5 1` - called **small-straight**;
- sequence from `2` to `6`, like `6 3 4 2 5` - called **big-straight**.

_(combinates named with two words are written with dash here for consistency with answers which our code
will produce)_

Such combinations increases player's score by different values, but it is not important now.

Our goal is to write a program which for given combination of dice will determine its type.

**Input data** contains a number of test-cases in the first line.  
Next lines contain `5` values each - points of player's dice.  
**Answer** should contain the name for each of combinations. Names could be `pair`, `two-pairs`, `three`,
`four`, `yacht`, `full-house`, `small-straight`, `big-straight` or `none`, separated with spaces.

Example:

    input data:
	3
	3 6 5 6 1
	1 6 6 1 6
	2 4 3 5 1
	
	answer:
	pair full-house small-straight

*You can read more about the game itself at wikipedia article on
[Yacht](http://en.wikipedia.org/wiki/Yacht_(dice_game)) - do not be surprised of slightly different combinations set,
it is not universally agreed upon.*