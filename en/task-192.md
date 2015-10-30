_This task is very similar to one given at [Facebook Hackercup](https://www.facebook.com/hackercup) event in Jan 2015 (qualification, problem #2).
We offer it to you so you can get better acquainted with problems of this popular contest and have greater motivation
to participate in future years._

Several mighty gangster clans are discussing the next great battle between them. They agreed on the following terms:

- each side can register any number of participants - e.g. there could be `7` gangsters of one clan against `11`
	ones of the other;
- each gangster should be armed with pistols and hand grenades - as many as he is willing to carry - i.e. one
	may bring `2` pistols and `13` grenades, while other could have `8` pistols and only `1` grenade;
- total amounts of weapons of each kind should be equal for both sides - i.e. if clan `A` has `50` pistols and
	`100` grenades - then clan `B` should arm their people to precisely the same figures.

Heads of the clans are now quite puzzled! Sides agreed to use `P` pistols and `G` grenades each.
Every member of every clan then reported how many things he has - let us say that `i`-th member of the clan has
`p[i]` pistols and `g[i]` grenades. And how then it is possible to pick members of the clan so that totals of
their arsenal equal to required numbers?

They ask you to write a small program to help them. It is guaranteed that each clan have at least one subset of
members satisfying the requirements. Of course if there are several choices, the one with more people should be
preferred (because we do not like gangsters and want as many of them to be killed as possible).

**Input data** will contain `N` the number of clans in the first line, then values for `P` and `G` will follow.  
Then all clans are described in `N` chunks of lines.  
Each chunk has a single value `K` at its first line - total amount of members.  
Then `K` lines will follow specifying `p[i]` and `g[i]` for a single member of this clan.  
**Answer** should have `N` values - for every clan the maximum amount of its members who can participate.

**Limits** are: `N <= 13`, `K <= 17`, `P <= 2000`, `G <= 3000`.

Example:
	
	input data:
	3 1717 2058
	7
	455 634
	414 774
	371 377
	436 557
	513 753
	803 496
	401 809
	7
	508 731
	854 556
	666 521
	274 987
	910 418
	249 1055
	807 1640
	5
	225 230
	501 503
	410 427
	381 570
	610 755
    
	answer:
	3 2 4

_Here from the first clan we pick members with `513`, `803` and `401` pistols, from the second ones with `910`
and `807`, and from the third - all except that with `410`._