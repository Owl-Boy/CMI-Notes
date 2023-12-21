# Fitting Manifolds to data in presence of noise
- Data points in higher dimensional spaces lie near a low dimensional sub-manifolds
	- A two-torus in a 2-dimensional manifold in a 3-dimensional ambient space
	- Example:
		- Cryo-electron microscopy
			- We want to picture macromolecules. so we shoot beams of electron at them and look at the shadows formed at a screen behind (not occlusion shadows)
			- reconstruction of atoms in a dimension as big as the number of pixels available, where each pixel gives an intensity when electron pass through for a given orientation
	- We deal with volume and reach of a manifold
		- make largest possible tangent spheres(both inside and outside) at all points. and pick the smallest one out of them. The radius of that sphere
	- Hausdorff distance : between two manifold. pick a point from one and get its distance from the other manifold, the largest among those is the Hausdorff  distance
- Weak Validity Problem
	- Oracle tells the distance between some manifold and some Hyper-plane
	- We can make the oracle with just the sample points (we want the find the distance between a manifold and the set of points in the sample)
	- It is possible to solve a Weak Optimization problem for a K in polynomial time given access to a weak validity oracle
	- The outer cones give a nice way to pick optimal points in the discrete case, although its import to pick vectors in the interior of the cone and not close to the boundary for stability.

> [!quote] 
> Exponential og 3 is small compared to 40,000