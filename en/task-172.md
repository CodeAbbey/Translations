<div class="centered">
	<img alt="measuring altitude of the cloud" src="http://s15.postimg.org/voo7gk3ff/cloud_height.png"/>
</div>

Supposing you have already learned [Tree Height Measurement](./tree-height-measurement), let us discuss more interesting task.
It could arose in two cases:

- either the tree we are measuring is not directly accessible (it is on the other bank of the river!) and we could not
	measure distance to it simply by walking;
- or we are trying to measure the altitude of a cloud (or aircraft, or even the moon) - any object which has no "trunk" to
	which we can walk to measure the distance.

We nevertheless can solve this puzzle! Look at the picture above - we need to make angle measurement twice (instead of once)
from two different points, and also measure distance between them. E.g. we choose two points (on the same line with
the tree or cloud) and take angles `A` and `B` from them. We could not measure distance `D2` (either because it is over the
river, or because an object have no vertical "trunk"), but we measure `D1` instead. Now we get the two equations involving
two tangents instead of one:

    H   =   tan(B) * D2
	H   =   tan(A) * (D1 + D2)   =   tan(A) * D1  +  tan(A) * D2

Now it should be easy for you to exclude unknown `D2` and calculate the height!

_Of course in real case it becomes bit more tricky since while you run distance between two points, the cloud can move
so it is better to have two observers performing synchronized measurements. Also for large clouds it is important to
choose a single point to aim both times._

**Input data** will contain the amount of clouds (or aircrafts) we are curious about.  
Each line describes `D1`, `A` and `B` for a single cloud.  
**Answer** should contain altitudes of the objects, rounded to nearest integer.

Example:

	input data:
	3
	1859 23.7740 53.8740
	1721 34.2290 68.1863
	1512 26.0048 53.1380
	
	answer:
	1207 1609 1163
