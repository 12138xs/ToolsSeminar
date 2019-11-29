# Summary

Title: Low-latency graph streaming using compressed purely-functional trees
Author :Laxman Dhulipala, Guy E.Blelloch and Julian Shun
Year: 2019

>* Q: What are the problems that the paper targets to solve?
>   A: To design a data structure that supports light-weight snapshots which can be used to concurrently process queries and updates, while ensuring that the data structure is safe for parallelism and achieves good asymptotic and empirical performance.

>* Q: Why they did this research or what is the motivation of this work?
>   A: Graph-streaming systems receive a stream of queries and a stream of updates and must process both updates and queries with low latency.  Existing frameworks are not concurrent, or giving up serializability. Existing snapshot-based systems are either very space-inefficient, or suffer from high latency on updates.

>* Q: What have they done in this work? 
>   A: They use a compressed fully-functional tree data structured called the C-tree to represent graphs, and design a graph-streaming framework called Aspen that is able to support concurrent queries and updates to the graph with low latency.