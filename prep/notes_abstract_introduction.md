## Abstract
- Sorting one of the most basic algorithmic problems
- adaptive sorting = algorithms perform better on inputs that are easier to sort
- therefore define measure of sortedness that captures features of the input, typically an entropy measure aim design algorithm that adapt to this measure

### First Part (Reg is Source and algorithm)
- Many of these measures have been studied
- Two natural questions
	- how do these measure relate to each other
	- are there algorithms that are adaptive to each measure
- answer to these questions by completing a hierarchy of relations between previously studied entropy measures
- this hierarchy has a source called Reg.
- an existing datastructure already yields a sorting algorithm adaptive to Reg -- also something we could prove
- Consequently this algorithm achieves the adaptive bounds of all other measures in the hierarchy

### Second Part (reg)
- McIlroy notes Reg has a mathematically inconvenient definition
- New more elgant measure reg
- if input contains no duplicates $O(n+log reg)=O(n + log Reg)$ -- this is something we could prove
- almost as strong, easier to analyse

### Third Part (sprout sort)
- reg adaptive algorithm in the offline binary search tree model
- single bst stores the distinct input keys which must be accessed in input order
- offline
- each access starts at the root, unit cost for pointer moves and rotations
- access cost of $O(n + log reg)$
- most adaptive algorithm in the BST model to date

### Fourth Part (skeleton sort)
- randomised pointer machine () algorithm
- sorts in O(n + log reg) does not work if the input has duplicates how to use in practice then

## Introduction
- we study comparison based adaptive sorting of n elements 
- and offline binary search tree access problem
- sorting n distinct elements requires $Omega(n log n)$ comparisons in the worst case cite proof
- some inputs are easier to sort than others this is not taken into account by this bound.
- if input is already sorted that can be verified in linear time
- and an almost sorted input can intuitively be sorted in shorter time
- adaptive sorting algorithms that exploit input features that reflect notions of almost-sortedness, expressed by entropy functions
- examples 
	- Powersort, inputs consisting of few sorted contigois pieces , few contigous blocks, increasing or monotone subsequences
- measures of entropy
- is one strictly stronger than the other, in the sense that matching one in running time, implies matching the other
- from this hieararchy developed
- for each measure one can ask whether there exists algorithms that are adaptive to that measure
- unified bound dictionary yiels Reg adaptive algorithm
- so this is the most adaptive sorting algorithm to date - but i mean only because its good for all the measures does this mean it is generally good How does this perform against something like merge sort
- then comes reg, dominates almost all prior measures
- if we have no duplicates then any reg-adaptive algorithm is also Reg-adaptive
- then two reg-adaptive algorithms
	- Skeleton Sort and Sprout Sort

### Questions until now

- The paper seems to show that they have a Reg adaptive algorithm from my understanding this should mean that this algorithm is adaptive to each other measure. But does that also really mean that the algorithm is good How does it compare to something like Merge Sort 
- As a follow up what does it really mean that their algorithm is adaptive to all other measures They say Consequently, this algorithm already achieves the adaptive bounds of all other measures in the hierarchy. What does this mean
- What is the connection to Power Sort PowerSort is an adaptive sorting algorithm but to what measure is it adaptive And lets assume its measure is in the hierarchy lower than the Reg adaptive algorithm is then the Reg adaptive algorithm also better
- Regarding the reg measure. It seems to be only good when we have no duplicates. How much worse is it when we have duplicates 
- As a follow up to the question before At least for Skeleton Sort they mention that it does not work if the input has duplicates. Then is the analysis and the algorithm by itself even interesting Is this really practical Because in practice it could never replace a sorting algorithm that has to work on arbitrary input. Of course we could do some preprocessing so that we kinda relax the input so that it doesn't have duplicates and then add the duplicates back in. But this would somewhat require a bit of overhead.