Once upon a time, when I was teaching electronics in the school, I was offering the following task to newcomers
in order to check their manner of thinking about problems:

*The girls are pasturing pigs at the field. In total they have `106` legs and `336` breasts. How many girls and pigs
are there?*

**Pigs** and **girls** were chosen not just for a joke! The main reason was that the number of breasts for a pig was
unknown. So some pupils were telling that "The problem could not be solved", while others were pretending that "there
are infinite number of solutions since we have `3` variables and `2` equations".

Of course it is not so! The variables in this problem have some obvious limitations, hence only quite finite amount of
solutions could be found - and of them only one looked believable.

---

Now you are to solve the "extended" version of the task. As before you will be given the number of legs and breasts and
your goal is to tell the number of possible solutions.

**Input data** will have the number of testcases in the first line.  
Next lines will contain a pair of values each - the amounts of legs and breasts - the first of them will always be
smaller than the second.  
**Answer** should give the amount of solutions for each case.

Example:

    input data:
	4
	6 10
	26 136
	106 336
	200 500
	
	answer:
	1 2 3 9

**Note:** of course we assume that all pigs have the same number of breasts because they are of the same breed -
otherwise the problem will become senseless. We also assume this number is even for pigs (as for most mammals), though
not limited from the top.

---

**Explanation**

For the input data `26` and `136` possible solutions are:

- `5` pigs with `26` breasts each (giving `20` legs and `130` breasts) with `3` girls;
- `1` pig with `114` breasts (mega-pig!) under the care of `11` girls.
