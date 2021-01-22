# Remarks On Metcalfe's Law
__Metcalfe's law__ says the value of a network grows proportionally to the square of the number of connected users.

In other words, it claims that the value is proportional to the number of edges in the network.

##### A quick intro to graphs

Properties of networks (or _graphs_) have been studied since Euler solved the Konigsberg bridge problem in 1736.

A graph is a discrete structure that is comprised of a collection of vertices (or nodes) and a collection of edges connecting vertices with each other.

The London tube map is a graph. Your family tree is a graph. And a social network is a graph.

Let G be a random graph with N vertices, connecting edges between any two vertices with probability p. Then the expected number of edges in G is p N(N-1)/2, because the maximally connected graph (the _complete_ graph) on N vertices has N(N-1)/2 edges.

Using _Big O_ notation we write that as O(N^2) which means that asymptotically it behaves like N^2, because as N goes to infinity the N^2 term dominates and we don't really care about the factor of p.

##### Back to valuation
Returning to Metcalfe's law, we see that it's really just saying that the value of the network is predicated on the number of edges, or the _connections_ between users.

But there are other network valuation models, notably:

- __Sarnoff's law__, which values the network proportionally to the number of users (the number of vertices in the graph) and therefore O(N).
- __Reed's law__, which proposes that the value of the network is proportional to the number of possible "subgroups" of users, which is O(2^N).

They're all getting the same thing, which is that the value of the network is something to do with the connectedness.

The degree of a vertex is the number of edges joining that vertex to other vertices in the graph. That's one way to think about connectedness.

A Sarnoff-type valuation would be suitable for a _starlike_ graph, where there is only one vertex of degree greater than two. A starlike network should therefore have a valuation which is O(N).

Reed's law says that the number of possible subgraphs is what matters, which could mean something like the number of possible subcommunties on Facebook or the number of Twitter cliques. Counting all the possible subgraphs in a naive way gives a valuation is O(2^N) by counting all possible subsets of the set of vertices.

But social networks typically exhibit clustering effects. Clusters are subgraphs with dense internal connectedness and sparse external connectedness.

Most people tend to have dense connections within their social circle and sparser connections outside of it. A minority of people are very densely connected (think influencers).

That means Reed's law radically overestimates the number of clusters we would see in a real network.

##### Beyond connectivity
Putting aside the problems with the valuation models, the concern with using Metcalfe's law on Bitcoin is that it makes no reference to the properties of the underlying protocol.

In other words, if the value is related to the number of edges, how is the Bitcoin network fundamentally different to the US postal service network, or the Herbalife distribution network?

Let's look at some of the essential features of the Bitcoin protocol that are different from social networks:

- It's a decentralised, peer-to-peer network and the network topology is inferred not explicit (see this [paper](https://arxiv.org/pdf/1812.00942.pdf), for example).
- Some of the nodes actively contribute to the security and integrity of the network through mining and validation.
- Proof-of-work requires a significant use of energy and computational resources, making attacks costly.

It's clear that while some of the value _could_ be tied to the connectedness, it's only as a proxy for what the network is actually doing - sharing and verifying transactions.

##### The value of complexity
The brilliance of Adam Back's original hashcash protocol was that it forced spammers to expend real computational effort to verify email headers, making it relatively unattractive to send spam.

This principle is the foundation of cryptography: I can't stop you trying to read my secrets, but I can make it so difficult for you to read them that you won't even bother.

Using a secure 256-bit symmetric encryption algorithm, it would take 2^256 attempts for an attacker to guess your password and decrypt your message. Since most attackers don't have the luxury of waiting around until the end of the universe, they won't bother trying.

The appeal of quantum computing, of course, is that instead of 2^256 attempts I only need 2^128 rounds of Grover's algorithm, provided I can actually build enough qubits.

But the point is that regardless of how you try to attack, it will cost you. Either you spend decades building a non-trivial amount of qubits, solve the error correction problem, and build quantum circuits for evaluating SHA-1 hashes, or you spend a lot of money on ASICs.

We know that a minority of human beings will always try to cheat and steal, all we can do is make the behaviour costly.

Mathematics is the best tool for the job, because we _know_ the computational complexity of 
