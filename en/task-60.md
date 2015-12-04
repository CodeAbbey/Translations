Here is a variation of another popular task for practicing **dynamic programming** approach (though of course precise
algorithm is not explained by these words).

<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="600px" height="100px">

	<g>
		<g stroke="black" fill="none">
			<ellipse cx="20" cy="70" rx="15" ry="12"/>
			<ellipse cx="60" cy="70" rx="15" ry="12"/>
			<ellipse cx="100" cy="70" rx="15" ry="12"/>
			<ellipse cx="140" cy="70" rx="15" ry="12"/>
			<ellipse cx="180" cy="70" rx="15" ry="12"/>
			<ellipse cx="220" cy="70" rx="15" ry="12"/>
			<ellipse cx="260" cy="70" rx="15" ry="12"/>
			<ellipse cx="300" cy="70" rx="15" ry="12"/>
		</g>
		<g stroke="none" fill="blue" text-anchor="middle">
		    <text x="20" y="76">11</text>
		    <text x="60" y="76">5</text>
		    <text x="100" y="76">3</text>
		    <text x="140" y="76">17</text>
		    <text x="180" y="76">2</text>
		    <text x="220" y="76">13</text>
		    <text x="260" y="76">19</text>
		    <text x="300" y="76">7</text>
		</g>
		<path d="M20,50 q40,-50 80,0 q60,-50 120,0 q40,-50 80,0" stroke="red" fill="none"/>
	</g>
</svg>
</div>


The Rabbit is going to cross the river. There is a straight chain of tiny isles across the flow and the animal should
jump from one to another because it surely could not swim.

At each of the isles there are some candies. When the Rabbit arrives to the new isle, it collects all the candies
here.

However, the Rabbit could not jump directly to the next isle in the chain - it just is too strong to make short jumps.
So, instead, it can jump over the one or two isles (i.e. from the `1st` for example to `3rd` or `4th` but not
to `2nd` or `5th` and further). Also the Rabbit could not jump back.

You can see the sample of the Rabbit's path on the drawing above. It visits `1st`, `3rd`, `6th` and `8th` isles and
collects:

    11 + 3 + 13 + 7 = 34

the amount of `34` candies. Obviously he could do better if the path is chosen more wisely.

**Your task is to choose the best path for Rabbit over the given chain of isles** - i.e. to maximize the amount of
the candies collected. Note that Rabbit starts from `1st` isle and finishes either on the `Nth` or `(N-1)th` where
`N` is the total number of isles (because from these two it will necessarily jump immediately to the other bank).

**Input data** will contain the number of test-cases in the first line.  
Next lines contain one test-case each - i.e. one chain of isles, described by the array of numbers - amounts of
candies at each isle.  
**Answer** should contain the maximum possible amount of candies gathered for each test case.

Example:

    input data:
	2
	11 5 3 17 2 13 19 7
	9 7 12 7 16 3 7 17 14 13 4 6 11 6 3 3 5 4 11 3 15 12 14 2 15 19 11 12
	
	answer:
	48 157
