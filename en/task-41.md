<!-- #Median of Three -->

You probably already solved the problem [Minimum of Three](./min-of-three) - and it was not great puzzle for you? Since
programmers should improve their logic (and not only skills in programming language), let us change the task to make
it more tricky.

You will be again given triplets of numbers, but now the middle of them should be chosen - i.e. not the largest and not
the smallest one. Such number is called the **Median** (of the set, array etc).

Be sure, this problem is not simply "another stupid exercise" - it is used as a part in powerful QuickSort algorithm,
for example.

**Input data** will contain in the first line the number of triplets to follow.  
Next lines will contain one triplet each.  
**Answer** should contain selected medians of triplets, separated by spaces.

Example:

    data:
    3
    7 3 5
    15 20 40
    300 550 137
	
	answer:
	5 20 300

Note: if your program will have a lot of if-else-if-else statements, then you are probably doing something wrong.
Simple solution should have no more than three of them.