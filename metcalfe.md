

# Remarks On Metcalfe's Law

__Metcalfe's law__ says the value of a network grows proportionally to the square of the number of connected users.

In other words, it claims that the value is proportional to the number of edges in the network.

Properties of networks (or _graphs_) have been studied since Euler solved the Konigsberg bridge problem in 1736.

A graph is a discrete structure that is comprised of a collection of vertices (or nodes) and a collection of edges connecting vertices with each other.

The London tube map is a graph. Your family tree is a graph. And a social network is a graph.

Let G be a random graph with N vertices, connecting edges between any two vertices with probability p. Then the expected number of edges in G is p N(N-1)/2, because the maximally connected graph (the _complete_ graph) on N vertices has N(N-1)/2 edges.

Using _Big O_ notation we write that as O(N^2) which means that asymptotically it behaves like N^2, because as N goes to infinity the N^2 term dominates and we don't really care about the factor of p.

Returning to Metcalfe's law, we see that it's really just saying that the value of the network is predicated on the number of edges, or the _connections_ between users.

But there are other network valuation models, notably:

- __Sarnoff's law__, which values the network proportionally to the number of users (the number of vertices in the graph) and therefore O(N).
- __Reed's law__, which proposes that the value of the network is proportional to the number of possible "subgroups" of users, which is O(2^N).

They're all getting the same thing, which is that the value of the network is something to do with the degree of connectedness.

The degree of a vertex is the number of edges joining that vertex to other vertices in the graph. That's one way to think about connectedness.

A Sarnoff-type valuation would be suitable for a _starlike_ graph, where there is only one vertex of degree greater than two. A starlike network should therefore have a valuation which is O(N).

Reed's law says that the number of possible subgraphs is what matters, which could mean something like the number of possible subcommunties on Facebook or the number of Twitter cliques. Counting all the possible subgraphs in a naive way gives a valuation is O(2^N) by counting all possible subsets of the set of vertices.

But social networks typically exhibit clustering effects. Clusters are subgraphs with dense internal connectedness and sparse external connectedness.

Mst people tend to have dense connections within their social circle and sparser connections outside of it. A minority of people are very densely connected (think influencers).

What that implies is that 
