# Graph-Drawing-Algorithms

This repository contains several graph drawing tools i made while working on my thesis for completing the BSc & MSc integrated diploma in Applied Mathematics and Physical Sciences @ National Technical University of Athens.  

      I will upload several parts of the project's code. For more details contact me at leandrosevag@hotmail.com

# 
**Abstract**

Monotone drawings of graphs is a relatively new method for visualizing graphs. A monotone drawing of a graph G is a straight-line drawing of G in a grid, where for every pair of nodes, there is a path between them which is monotone with respect to some direction. The subject of this diploma thesis is the implementation and experimental evaluation of certain algorithms for monotone drawing of a special class of graphs, trees.
We first show that all rooted trees can be represented with balanced strings of parenthesis and we describe the procedure through which this is done. Using this fact, we describe two algorithms for generating rooted trees exhaustively and randomly. For the implementations, we developed an interactive tool which applies the algorithms to a user selected tree, and visualizes their drawings. For the evaluation part, we generate a set of distinct rooted trees, we apply the algorithms to them and we save the grid dimensions of their drawings in a database. Next, we analyze the data and we compare them with the theoretical grid size of the algorithms, in order to compute the maximum portion each one of them used. 

**Example  (from Angelini et al. paper) :**

![ex](https://i.ibb.co/x8fhRTT/angelini-et-al.png)

**Practical Example 1 (from our implementation):**

We can see how much better understanding of the graph we get from the monotone drawing. 

![mon](https://i.ibb.co/DzPNh1F/mon.png)

**Practical Example 2 (from our implementation):**

Ternary tree with three levels, using three of the algorithms

![algos](https://i.ibb.co/qM00fps/algos.png)


## Technologies used in this project

![techs](https://i.ibb.co/qdfX2gc/techs.png)


## Introduction 

From Wikipedia:
> In graph theory, a tree is an undirected graph in which any two vertices are connected by exactly one path, or equivalently a connected acyclic undirected graph

Tree Example:

![tree](https://i.ibb.co/rvTMb1S/unnamed0.png)

Every tree can be represented as a balanced set of open and closed parenthesis. The order of the nodes is also maintained. An example can be seen below. Starting from the root, every time we see an open parenthesis we move downwards and create a new node, else we go backwards. And we do this in counter-clockwise direction.

![trees](https://i.ibb.co/Xt9RTYZ/Untitled.png)

We know that every Tree can have a monotone drawing. In order to draw more general graphs, we compute a spanning-tree , draw it monotonically, and then add the extra edges. 

![mon](https://i.ibb.co/bLvL2ZF/Picture1.png)

This is why Monotone Drawings of Trees receeived much attention from researchers. 

In my thesis. I created a database from all distinct rooted trees with up to 15 nodes. I then implemented almost all of the known algorithms for monotone drawings of trees using Python and tested them on the database in order to analyze and compare their results in terms of grid size.
Also, i made a tool using HTML-JS-PHP-SQL-Python where a user can do one of the following tasks:

- **Use and visualize monotone drawing algorithms for an input tree **

  ![main page](https://i.ibb.co/4Ptx5f0/Capture001.png)
  ![algos](https://i.ibb.co/qM00fps/algos.png)

- **Import/Export graphml files**

- **Random Tree Generation**

- **Visual comparison of different algorithm grid-size utilization**
  ![comparison](https://i.ibb.co/7bb5YNX/algorithm-comparison.png)
  
- **Access to the database (Retrieve and visualize data)**
  ![databsae](https://i.ibb.co/WvDDm2t/Capture14.png)
  ![database2](https://i.ibb.co/fDn4X3z/Capture15.png)

### The implemented algorithms with their grid size utilization can be seen below:

Algorithm papers:
  - Angelini et al. BFS and DFS [[1]](#1)
  - Kindermann et al. [[2]](#2)
  - He & He [[3]](#3)
  - Oikonomou & Symvonis  [[4]](#4)


![algorithms](https://i.ibb.co/gTRdn2r/algorithms.png)
      
      
Most of the algorithms use computational geometry and number theory for generating the "angles" assigned the edges of the graph. In particular, the Stern-Brocot Tree and the Farey Sequences are mostly used. The alogorithms of Oikonomou-Symvonis are the only ones not relying on number theory. They use a clever algorithmic way of assigning angles using basic geometry and they are the easiest to understand and implement. 

## Tree Generation

I include some algorithms for tree generation (as balanced set of parenthesis) and convertion to networkx datatype.

For a random tree we can compute a random valid string of parenthesis. The complexity of creating a random tree is   <img src="https://latex.codecogs.com/png.latex?\inline&space;O(n^{1.5})" title="O(n^{1.5})" />

For generating all distinct trees with n nodes, the computational complexity is   <img src="https://latex.codecogs.com/png.latex?\inline&space;O(\frac{4^{n}}{n^{1.5}})" title="O(\frac{4^{n}}{n^{1.5}})" />



## Results

### Comparison of generated data with each algorithm's theoretical grid size.

![results](https://i.ibb.co/FWLLGMM/res.png)

![results graph](https://i.ibb.co/3SJhpZm/Picture2.png)


## References

<a id="1">[1]</a> 
Journal of Graph Algorithms and Applications. Monotone Drawings of Graphs. 
Patrizio Angelini, Enrico Colasante, Giuseppe Di Battista,Fabrizio Frati,Maurizio Patrignani
[paper](https://www.emis.de/journals/JGAA/accepted/2012/Angelini+2012.16.1.pdf)

<a id="2">[2]</a> 
On Monotone Drawings of Trees
Philipp Kindermann, Andre Schulz, Joachim Spoerhase, Alexander Wolff
[paper](https://arxiv.org/pdf/1505.01410.pdf)

<a id="3">[3]</a> 
Optimal Monotone Drawings of Trees
Dayu He, Xin He
[paper](https://arxiv.org/pdf/1604.03921v1.pdf)

<a id="4">[4]</a> 
SIMPLE COMPACT MONOTONE TREE DRAWINGS 
ANARGYROS OIKONOMOU, ANTONIOS SYMVONIS
[paper](https://arxiv.org/pdf/1708.09653.pdf)







