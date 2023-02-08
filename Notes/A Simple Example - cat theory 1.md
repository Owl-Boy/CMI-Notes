202301270201

Type : #Example 
Tags : [[Category Theory]]

---
# A Simple Example - cat theory 1
Consider three points; call them ●, ○ and ∗.
Here the _system:_$S$ will simply be a way of connecting these points together. This connection can represent points as sites on a power grid, or a system describing connection by power lines. or as people susceptible to some disease, with a system describing interactions that lead to contagion.

An example of such a system would be like:
![[20230127_03h05m30s_grim.png| center|150]]
The connections are symmetric and transitive so friendship cannot be represented by the system as a it is not transitive( A friends' friend is not necessaritly a friend) but a disease or a possible communication can be.
Two more systems can be 

![[20230127_03h10m05s_grim.png| center | 420]]
Now we define an observation $\Phi:S\to Boolean$, which is if ● is connected to ∗.
There are a total of $5$ systems and $\Phi$ assigns `true` to the following systems

![[20230127_03h31m37s_grim.png| center | 420]]
and it assigns `false` to the remaining systems
![[20230127_03h33m25s_grim.png| center | 550]]

The last part of the setup is the sort of operations that we want to perform on the system, one common example is called _join_. The idea being that the connectivity observations will not be compositional with respect to the _join_ operator, which will be the [[Generating Effects| generative effect]]. 

The **Join** of two systems $A$ and $B$ is performed by combining their connection, denoted by $A\lor B$ 
![[20230127_03h45m38s_grim.png| center | 500]]
The last example joins two systems that are assigned `false` by the $\Phi$ but their join is assigned `true`. Hence the observation is lossy under $\Phi$ and a more detailed observation is needed which also inclued ○.  

---
# References
[[Generating Effects]]