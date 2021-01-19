# Graph-Drawing

Several Graph Drawing tools i made while working on my thesis on Monotone Drawings of Trees, using Python and NetworkX.

Monotone Drawings of Graphs is a new standard of graph drawing, introduced by Angelini et al. [link](https://www.emis.de/journals/JGAA/accepted/2012/Angelini+2012.16.1.pdf)


# Introduction 

Every tree can be represented as a balanced set of open and closed parenthesis.The order of the nodes is also maintained. An example can be seened below. Starting from the root, every time we see an open parenthesis we move downwards and create a new node, else we go backwards. And we do this in counter-clockwise direction.

![trees](https://i.ibb.co/Xt9RTYZ/Untitled.png)
