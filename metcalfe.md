# Remarks On Metcalfe's Law
__Metcalfe's law__ says the value of a network grows proportionally to the square of the number of connected users.

In other words, it claims that the value is proportional to the number of edges in the network.

##### A quick intro to graphs

Properties of networks (or _graphs_) have been studied since Euler solved the Konigsberg bridge problem in 1736.

A graph is a discrete structure that is comprised of a collection of vertices (or nodes) and a collection of edges connecting vertices with each other.

The London tube map is a graph. Your family tree is a graph. And a social network is a graph.

Let G be a random graph with N vertices, connecting edges between any two vertices with probability p. Then the expected number of edges in G is p N(N-1)/2, because the maximally connected graph (the _complete_ graph) on N vertices has N(N-1)/2 edges.

Using _Big O_ notation write that as O(N^2) which means that asymptotically it behaves like N^2, because as N goes to infinity the N^2 term dominates and we don't really care about the factor of p.

##### Back to valuation
Returning to Metcalfe's law, you see that it's really just saying that the value of the network is predicated on the number of edges, or the _connections_ between users.

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

A minority of human beings will always try to cheat and steal, all you can do is make the behaviour costly.

Mathematics is the best tool for the job, because we _know_ that computational complexity is universal. If quantum computers become a reality, we have lattice cryptography and bigger keys. But fundamentally at no point are we relying on trust or obscurity to protect us.

_(As an aside, structurally the argument that quantum computing invalidates Bitcoin is essentially the same as the one that says gold mining on asteroids invalidates gold. Both assume that future technologies will make a difficult problem trivial.)_

The Bitcoin protocol also incentivises good behaviour by issuing rewards for securing the network. This encourages the network to grow in a way that maintains security and makes attacks more costly.

Therefore any valuation model has to look at _both_ the underlying protocol and the network, it can't look at them in isolation.

It can't _just_ be computational effort, because distributed computing networks solving protein folding would have the same kind of value.

What's more, it can't _just_ be security and connectedness that make Bitcoin worth something, because Signal has both of those features. The decentralisation and proof-of-work are vital components too. You can't use Signal to maintain a consistent, distributed ledger.

##### Everything is energy

_Write here about how, at bottom, everything is about energy consumption, including gold. Dr. Chris Dark podcast reference..._

##### Money: the good, the bad, and the "hard"

The concept of "hardness" of money continues to baffle me. Here's a great example:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">My theory of why hard money lowers time preference in a tweet:<br><br>The harder the money, the more likely it is to hold value for the future. The more you can send value to the future, the less uncertain the future becomes, the less you discount the future.</p>&mdash; Saifedean.com (@saifedean) <a href="https://twitter.com/saifedean/status/1342913179098243073?ref_src=twsrc%5Etfw">December 26, 2020</a></blockquote>

Imagine you go away, read The Deficit Myth, and have a Damascus road moment. Let's rewrite that in MMT terms:

> My theory of why **debt driven infrastructure spending** lowers time preference in a tweet: The **greater the debt driven infrastructure spending**, the more likely it is to **create** value for the future. The more you can send value to the future, the less uncertain the future becomes, the less you discount the future.

What part of that was dependent on "hard money"? Precisely nothing. That means the concept doesn't meaningfully capture the essential features of the underlying.

You could also plant date trees, wait 20 years, and have successfully transmitted value to the future.

It should be obvious that discounting can _never_ explain the time-dependent properties of money because discounting itself is an attempt to fix the lack of time-dependent dynamics in traditional economics. In other words, without understanding ergodicity you can't hope to properly model this concept.

But before you can talk about how hard (or soft?) money is, you need to agree on what money is first.

Mike Green very eloquently describes money as _"that which extinguishes debt."_

With that definition in mind, a structural defect is therefore the inability to create more Bitcoin when it is lost.

If I owe you 1 Bitcoin and I lose access to my wallet (it can happen to anyone, even Peter Schiff), I can never recover that Bitcoin and now instead of twenty one million Bitcoin there are twenty million nine hundred ninety-nine thousand nine hundred ninety-nine Bitcoin.

Of course, historically we have lost plenty of gold too, indeed people still comb farmer's fields in England looking for Roman gold (and occasionally find it).

But the difference is that Bitcoin has a fixed algorithmic schedule and gold is ad hoc, we know that it has to run out eventually but we don't know precisely when.

I think this criticism is one of the most perceptive, because it identifies why the "hard money" idealists like Bitcoin:

- The emphasis on personal responsibility and prudence over forgiveness.
- Scarcity and permanence that allow those who have "earned" wealth to keep it forever.
- It realises the libertarian ideal of opting out of a bloated, corrupt government system.

None of those things are unique to Bitcoin, however, so any criticism could equally be applied to land. Land shares many of the same features: early adopters locked in incredible gains and there is highly concentrated ownership. That's why comparisons have been made between Bitcoin and feudalism. But it's hard to find an asset class that doesn't have those properties in some degree.

Putting all of that aside, the practical point of how you deal with lost Bitcoin is an important one that needs to be addressed _if_ you want Bitcoin to be used as money. I'm not convinced that Bitcoin _needs_ to be money to have value, however.

And if Bitcoin is money, is it really obeying Gresham's law? The only way to test that would be if you could buy your groceries with Bitcoin. Then it would be clear what type of money people prefer, given the choice. But for now it is completely unfalsifiable and therefore worthless.

You can't, for example, claim that dollars are better than casino chips because nobody accepts casino chips outside of the casino.

What's the value of Bitcoin then?

##### Intrinsic value

I often see people claim that Bitcoin has no "intrinsic value." Of course, there is a vast body of philosophical work on this notion which those people have never and will never read. But you should never let that get in the way of a high-engagement Twitter thread.

In very simple terms, intrinsic value means the value of Bitcoin that doesn't relate to something else. This is entirely separate from the extrinsic value or the final value - the value of Bitcoin for it's own sake. There's probably no way we can ever know or agree on the intrinsic value of Bitcoin, or indeed anything at all, so it's a rather silly thing to discuss.

The value of Bitcoin for it's own sake could be something like the intellectual value of the Satoshi whitepaper and the innovation it sparked.

Of course there is no underlying asset or cashflow, like a company. But what is a company? It's a legal entity. It has accounts with numbers that tell you about the asset it holds, the liabilities, the cashflow, and so on. All you have as a shareholder is a claim on some of that cashflow.

There is no guarantee that a company which exists today will exist 10 years from now, or that any of the employees will be the same, and the cashflow you have a claim on could increase or decrease.

A discounted cash flow is an infinite series, but does anyone think Apple will exist for an infinite amount of time?

It's an abstraction that allows you to put a definite number to it, which you can use as a tool for comparison.

Nobody has come up with a good abstraction for Bitcoin yet.

Given that almost everyone disagrees on the valuation model for Bitcoin - or that it even has value - is it any surprise that it's volatile?

##### Putting it all together
TBC
