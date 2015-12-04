_Thanks a lot to [Gaurav Kamath aka Moriarty](../user_profile/gauravkamath108) for suggesting such an nice problem!_

This popular game was probably invented by **Lewis Carrol**, the author of "Alice in Wonderland" at `1877`.

You are given two words of the same length, and it is required to convert one into another with several steps. Each
step consists of changing a single letter so that still existing vocabulary words are produced. Here is the ladder
with goal of feeding `HAY` to the `COW`, for example:

    HAY  ->  BAY  ->  BOY  ->  TOY  ->  TOW  ->  COW

Let us write a program searching for the shortest path between two words!

We will use our dictionary which you can download by this link:
[right-click and choose "Save as", please](http://www.codeabbey.com/data/words.txt).

Our game will use words of `5` letters - any you will find in this list, including plurals like `books` and verbs in
past like `bowed`.

**Input data** contains a number `N` of word pairs to process.  
Next `N` lines contain two words each.  
**Answer** should contain minimum length of the path between words for each pair - i.e. the total count
of words in the chain, including starting and ending ones.

Example:

    input data:
	2
	girls women
	mayor clown
	
	answer:
	9 14

Here the following paths are possible:

	women woken token tokes tikes tiles tills gills girls
	
	mayor manor minor miner mines miles moles molts moots boots blots blows blown clown
