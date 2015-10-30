<div>
<img alt="four pics one word screenshot" src="http://s16.postimg.org/bedpe4qud/4pics1word.png" align="right"/>
</div>
Here is the problem suggested by [Guy Gervais](../user_profile/guygervais1). I dare to cite his letter:

*I got the idea from watching my wife play one of those "4 images, 1 word" games on her tablet.
Often, she'll get stuck and ask me for help; and then I get  stuck too. :-) To help my wife in her games, I made an
app that will accept the candidate letters, the word length and use a list of words to give all the possibilities.   
Here is the [link](http://www.windowsphone.com/en-ca/store/app/4-pics-1-word-helper/a8bd1c90-9c8b-40bc-ae60-6d79606161c8).*

*So the idea is basically to give a word list to the user (everyone uses the same word list) with a number of random
letters and a desired word length; the goal is to find all the possible words in the list. The results could be to
count the words...*

My wife also plays this game sometimes. I dare to retell the rules - user is given `4` images and a handful of letters.
The goal is to guess the word described by these images which could be built of these letters.


So you see, you are to write the program which searches through the dictionary for suitable words. As a matter of
fact it is the advanced version of [Anagrams](./anagrams) because it is not necessary to use all letters.

[Download dictionary file by this link](http://www.codeabbey.com/data/words.txt)

**Input data** contain the number of testcases in the first line.  
Each of the following lines contains the required length of the word and a set of letters.  
**Answer** should contain the amount of words from dictionary satisfying each case.

Example:

    input data:
	2
	3 t c a z
	3 t c a f
	
	answer:
	2 4

*First case allows words `cat` and `act` while second adds `fat` and `aft` to them.*

<script>
noServerRun = true;
</script>