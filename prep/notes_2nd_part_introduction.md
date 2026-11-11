## Terminology 

The following abstractions of adaptive sorting bounds:

- $\mathcal{I}_n$ is the set of all size-n inputs
- *notion of presortedness*: assigns every input $X\in\mathcal{I}_n$ some target cost $f(X)$, so basically is a notion of presortedness a function $f$ mapping $I_n\rightarrow \mathbb{N}(?)$
- Definition (Comparison-adaptive): If it sorts every input $X$ in $O(f(X))$ comparisons
- Definition (Time-adaptive): if total running time is $O(f(X))$

### Offline BST Algorithm
> For offline BST algorithms, we consider the BST model where one can navigate and rotate nodes of a binary search tree, and we consider the total access cost of accessing all elements of $X$ in-order.



- Target $f$ is *usually* defined in two steps:
	- first a number $k(X)$ is defined in a sophisticated way (wtf means sophisticated way?)
	- f(X) is a function of $n$ and $k(X)$ 
	- concrete example in knuths volume 3 somewhere 
	- todo look it up, but what he is basically doing is split the input into non decreasing sequences then we have so called runs call the amount of runs nRuns then put $f(x)=n(1+log(nRuns))$ and then we present a comparison-adaptive algorithm 
	- but this is somehow weird I mean then really something like the following could happen. Make $f(x)=k(x)^n$ and then basically every stupid sorting algorithm we can look at is comparison adaptive???

## Ranks and Duality
- Take list $X$ of elements and $x\in X$ rank of $x$ denoted by $rank_X(x)$ is the index in the sorted order, after removing duplicates
- replacing each element $X[i]$ by its rank is isomorphic to keeping the original input. thus we can consider each $X$ as a list in $[n]$.
- If $X$ contains no duplicates it is a permutation
- Permutation has an inverse ofc the permutation that is reversing everything so that we have natural order again
- the inverse we now (due to whatever reason) give it another name dual. we could just keep it we the mathematical rigorous inverse but okay have to remember yet another name
- dual runs: nRuns*(X):= nRuns(X^{-1}).
- **why the f is nRuns now a function before it was a number, just the amount of Runs we had this is shitty non rigorous notation**
- dual stuff first only works when we have no duplicates
- but can be manually extended to inputs X with duplicates
- Definition (value-contigous): A subsequence $X_I\subset X$ is value-contigous if for all $x,y,z\in X$ with $x\leq y\leq z$ and $x,z\in X_i$, we also have $y\in X_i$
- We can partition X into maximal non-decreasing value-contigous sequences $X_i$ (CAN WE REALLY? HAVE TO LOOK AT EXAMPLE) and put $nRuns*(X)=k$ huh? what is the k now? I mean we have before that k is the amount of runs. but now we just say that the amount of runs is the amount of runs? 

> We ocasionally define duality for lists with duplicates, by considering the position of the i'th element in the sorted order after a stable sort, denoted $\overline{X}[i]$. Note that $\overline{X}$ is a permutation. 

Wtf is now $\overline{X}$? 

