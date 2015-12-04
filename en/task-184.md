_Thanks to [Graeme Yeandle](../user_profile/quandray) for suggesting this problem!_

<div class="centered">
<img src="http://s14.postimg.org/e9ngig581/heap_of_matches.png" alt="person puzzled at heap of matches"/>
</div>

This is a game for two players - you can find its variations in books about popular math.

Two players have a heap of `M` matches. Each player in turn should take up to `K` matches from it, thus reducing the heap.
One who takes the last match - wins.

For example, here `5` matches and each player can take up to `3` in turn. The first player can win picking `1` match
at first - then for any response of the opponent it is possible to secure all remaining matches.

"Inverse" variation of winning rule also exist - who takes the last match - loses the game.

###Problem Statement

You will be told `M` and `K` and also whether the winning rule is "normal" or "inverted". Your opponent offers you to make
the first move if you want. If you agree, you should tell which first move can secure a win for you (if further you play
optimally).

**Input data** will contain amount of test-cases in the first line.  
Each line contains integers `M` and `K` and also letter `n` for normal rules or `i` for inverted.  
**Answer** should tell your first move for each case or `0` if you want your opponent to move first.

Example:

    input data:
	3
	5 3 n
	9 4 i
	3 2 n
	
	answer:
	1 3 0

If this puzzle was too easy for you, try the altered version of the game in the [Simple Game of Sticks](./simple-game-of-sticks)!
