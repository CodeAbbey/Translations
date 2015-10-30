<!-- #Title -->

The task [Matching Words](./matching-words) allows easy but ineffective solution because it works with very small input
data.

This problem is similar, but you will need to proceed almost one million words and choose a single, most frequent of
them - it is very often and very important task - for example performed by search engines over web pages. You will
need to use efficient algorithm, otherwise your program will work for hours and perhaps days.

Since it is not practical to provide test-cases consisting of so many letters along with problem statement, you will
generate the words yourself.

Use algorithm from the task [Funny Words Generator](./funny-words-generator) to create a list of exactly `900000`
words, each `6` letters long.  
You should use exactly the same Linear Congruential Generator as random generator. The only input parameter would be
**the seed** for your random number generator (LCG).

**Input data** will contain a single value - the seed for random generator which you will use to generate list of words.  
**Answer** should contain a single word - one most frequently encountered in the list.

Example:

    input data:
	99658
	
	answer:
	riguzi

*Test-cases are selected so that there would be only one most frequent word for each given seed.*