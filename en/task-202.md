_Great Thanks to [Sergey Pobezhimov](../user_profile/moffserge) for helping to eliminate the bug in this problem!_

There is a great celebration. There are guests - `N` gentlemen and `N` ladies. Now they are to be organized
in pairs for the great dance. However women are capricious - each of them will agree to dance only with
very certain partners she likes. So master of ceremonies is having hard time trying to make as many
pairs as possible. Please, help him in this task!

Ladies are numbered with integers from `1` to `N`. Gentlemen have numbers from `N+1` to `2N`.
For each lady you are given numbers of partners with whom she is ready to make a pair.

**Input data:** first line contains value `N`.  
Next lines have the `id` of lady with a colon and then a list of `id`-s of gentlemen with whom she
is ready to dance.  
**Answer** should give a single value - maximum possible amount of pairs.

Example:

	input:
	19
	1: 25
	2: 20 25 28
	3: 27 32 37
	4: 22
	5: 32 38
	6: 32 34 35
	7: 22 34 37
	8: 30 35 38
	9: 20 23
	10: 24 29
	11: 29 32
	12: 23 26 31
	13: 21 25 34
	14: 21 27
	15: 20
	16: 23 31 38
	17: 22 27 28
	18: 35
	19: 24 25
	
	answer:
	17