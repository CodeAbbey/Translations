<!-- #Cards Shuffling -->

*Note: you may find it useful to solve [Card Names](./card-names) before this*

For any type of card game it is important to be able to shuffle the deck. Since only few of the programming languages
have built-in functions to randomly shuffle an array (like **PHP**) it is necessary to learn some useful algorithm.

Let us agree to use the following symbols to describe cards:

    ranks: A, 2, 3, 4, 5, 6, 7, 8, 9, T, J, Q, K
	suits: C, D, H, S

so that `CQ` is the "Queen of Clubs", `HT` is the "Ten of Hearts", `D2` is the "Two of Diamonds" and `SA`
is the "Ace of Spades".

There are `52` cards in total, so they should be put into an array of `52` elements before shuffling. Initial ordering
of the array is the following: 13 cards of Clubs, then 13 cards of Diamonds, then 13 cards of Hearts and at last 13
cards of Spades. Inside of each suit cards are arranged from Ace to King, so the whole deck looks like:

    [ CA, C2, C3, ..., CQ, CK, DA, D2, ..., DK, HA, H2, ..., HK, SA, S2, ..., SK ]

Then you should for each card generate some random number in the range `0 ... 51` and swap this card with another,
occupying the selected position (let indexes of array start from `0`). This may look like:

    FOR i = 0 ... 51 :
	    LET j = RANDOM(0 ... 51)
		SWAP deck[i] WITH deck[j]

For example, we take the first card `CA` and generate random value `15` for it - this means that card should be moved
to position 15, where `D3` was - and `D3` should be moved back to position `0`. Then we take `C2` from the position
`1` and generate next random number `50` - so `C2` is swapped with `SQ`. And so on.

You will be given the sequence of non-negative integer random numbers - if they are greater than necessary, trim them
to required range by taking `modulo 52`, like in the [Double Dice Roll](./double-dice-roll) task. Perform the
shuffling and print the new order of cards as an answer.

**Input data** will contain 52 non-negative integer numbers, which you should use to shuffle the deck as described.  
**Answer** should contain cards from shuffled array, separated with spaces.

Example (long lines wrapped):

    input data:
	5814 1316 2080 2712 0 647 8098 315 44 6354 7867 100 61 763 6731 685 42 9309 569 92 701 562
			85 8311 698 220 929 71 684 518 113 61 19 168 745 16 655 9548 6018 2686 25 785 81 721
			964 85 44 614 4 509 8708 19
	
	answer:
	C5 D5 S4 C8 CQ S3 HK C9 H3 H6 D3 ST DT HT C6 CK DA H9 SJ SK DK C2 DQ S5 H4 D7 S7 S2 C4 D9 CT
			HJ HQ D2 SA CA H5 H2 C7 D4 CJ D6 S9 HA S8 D8 S6 SQ C3 DJ H8 H7
