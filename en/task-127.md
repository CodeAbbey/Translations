*The idea proposed by [Guy Gervais](../user_profile/guygervais1) was so fruitful that it allows to create more than
one problem from it. Here is the simpler one.*

In many natural languages we can find some pairs of words which could be transformed to each other by changing the order
of letters. I.e. they consist of the same set of letters, for example:

   cat - act
   take - teak
   ate - eat - tea

Such words are called **anagrams** and as we see in the third example sometimes there are more than two words.

Your task is to find out the amount of anagrams for given word by the dictionary.

[Click this link with right mouse button and select "Save As" to download dictionary file](http://www.codeabbey.com/data/words.txt)

*Dictionary file contains a list of english words, one per line. It was taken from Ubuntu linux distribution and
stripped of words containing capital letters, apostrophes and non-english letters.*

**Input data** will contain the number of test-cases in the first line.  
Next lines will contain a single word each.  
**Answer** should contain the number of anagrams for each word (not including the word itself).

Example:

    input data:
	3
	bat
	coal
	lots
	
	answer:
	1 1 2

<script>
noServerRun = true;
</script>