<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="600px" height="120px">
	<g transform="translate(50,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 50,60, L 100,10 150,60 125, 110L"/>
			<path d="M 150,60, L 175,110"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
			<circle cx="50" cy="60" r="8"/>
			<circle cx="150" cy="60" r="8"/>
			<circle cx="125" cy="110" r="8"/>
			<circle cx="175" cy="110" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
			<text x="50" y="60">2</text>
			<text x="150" y="60">5</text>
			<text x="125" y="110">4</text>
			<text x="175" y="110">8</text>
		</g>
	</g>
</svg>
</div>

*If you know what Tree is, how search in it and building from sequence of
values are performed - then feel free to jump to [Problem Statement](#prob-stat) directly.*

**Tree** is a data structure very popular in programming. Just imagine - each web-site usually have some database,
each database is usually built of tables, each table usually have one or more indexes - and these indexes are usually
implemented as trees.

There are many types of trees - binary and non-binary, with many algorithms of self-balancing etc. However we'll start
with one of the simplest forms.

Let us agree that tree consists of **nodes**, and each node contains:

- some value (part of data stored inside the tree);
- left and right branch.

The branches of the node could be either **empty** or linked to some node (one branch to one node). No loops of links
may exist and so there is always some **root** node.

Look at the picture above: here the node marked with `3` is the root. Its left branch have a subtree consisting of a
single node `2`, and node `2` has both its branches empty. Right branch of `3` leads to node `5` which have both
branches leading to two more nodes.

Nodes without branches are sometimes called **leaves** (i.e. `2`, `4` and `8` in our example). Some tree architectures
do not store values in the nodes other than leaves. Though it is not our case.

**SEARCH IN A TREE**

Note that our sample tree have a nice property - all left children of the given node contain smaller values, while all
right children contain greater values. So if we want to find out whether the tree contains value `4` we can do the
following:

- check the root, it has value of `3` which is less than we want, so go to the right branch;
- we came to node `5` - it is now greater than the value we look for, so go to its left branch;
- we came to node `4` - that is what we wanted!

In case if we seek for value `6` we will end at the node `8` from which we want to go to the left, but it have its
left branch empty - so we conclude there is no such value in the tree at all.

So our tree is **binary** (because each node have no more than two children) and it has **ordering** allowing us to
find values without checking the whole tree.

**BUILDING PROCESS**

Suppose we have an array of values, like this `(3, 5, 4, 2, 8)` and we want to build a tree from it to simplify search
as explained above. The building algorithm looks quite similar to search - we need to "search" for element and when
we find the place where it should be, but there is an empty branch - we just insert new node here:

- as the root is empty, place the first number `3` here;
- to insert `5` we check the root and since `3` is less, we go to right - this branch is empty, so create new node
    here with `5` as a value;
- with `4` we go from `3` to right, then from `5` to left - and this left branch is empty, so hang new node with `4`
    here;
- next value `2` should go to the left of `3`, there was nothing before so create node with `2` as left branch of `3`;
- at last `8` goes to the right of `3` and to the right of `5` and makes new node there.

<div>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="850px" height="120px">
	<g transform="translate(0,0)">
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
		</g>
	</g>
	<g transform="translate(150,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 100,10 L 150,60"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
			<circle cx="150" cy="60" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
			<text x="150" y="60">5</text>
		</g>
	</g>
	<g transform="translate(300,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 100,10 L 150,60 125, 110"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
			<circle cx="150" cy="60" r="8"/>
			<circle cx="125" cy="110" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
			<text x="150" y="60">5</text>
			<text x="125" y="110">4</text>
		</g>
	</g>
	<g transform="translate(450,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 50,60, L 100,10 150,60 125, 110L"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
			<circle cx="50" cy="60" r="8"/>
			<circle cx="150" cy="60" r="8"/>
			<circle cx="125" cy="110" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
			<text x="50" y="60">2</text>
			<text x="150" y="60">5</text>
			<text x="125" y="110">4</text>
		</g>
	</g>
	<g transform="translate(600,0)">
		<g stroke="#777777" stroke-width="1" fill="none">
			<path d="M 50,60, L 100,10 150,60 125, 110L"/>
			<path d="M 150,60, L 175,110"/>
		</g>
		<g fill="white" stroke="red" stroke-width="1">
			<circle cx="100" cy="10" r="8"/>
			<circle cx="50" cy="60" r="8"/>
			<circle cx="150" cy="60" r="8"/>
			<circle cx="125" cy="110" r="8"/>
			<circle cx="175" cy="110" r="8"/>
		</g>
		<g fill="blue" stroke="none" text-anchor="middle" transform="translate(0,5)">
			<text x="100" y="10">3</text>
			<text x="50" y="60">2</text>
			<text x="150" y="60">5</text>
			<text x="125" y="110">4</text>
			<text x="175" y="110">8</text>
		</g>
	</g>
</svg>
</div>

**PROBLEM STATEMENT**
<a id="prob-stat"></a>

You are to create binary ordered tree from sequence of numbers as explained above (without caring of rebalancing it).
For each next number simply find the place where it should be inserted and add it there.

To represent the output, use the following format:

- each node is written as `(left,value,right)`;
- the `value` is always a number;
- branches `left` and `right` could be empty, which is specified with dash `-`;
- if branch is not empty, it should contain another node.

The tree from the picture above will be represented as:

    ((-,2,-),3,((-,4,-),5,(-,8,-)))

**Input data** will contain the length of array which should be converted to tree.  
The next line will contain the array itself - integers, separated by spaces.  
**Answer** should contain the tree description in the format specified above.

Example:

    input data:
	5
	3 5 4 2 8
	
	output data:
	((-,2,-),3,((-,4,-),5,(-,8,-)))
