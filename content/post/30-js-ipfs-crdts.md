---
date: 2017-07-13
url: 30-js-ipfs-crdts.md
title: Decentralized real-time collaborative conflict free editing in the browser using js-ipfs and CRDTs
author: Pedro Teixeira
---

While pubsub typically doesn't guarantee delivery or even order (this is the case), it allows for several use cases that still present the potential of it being very useful as a transport layer. By forming ad-hoc sets of nodes, nodes can come in and out of a cluster, and participate in a higher level protocol.

One set of these use cases are when nodes need to collaborate in writing on a shared data structure

Moving away from centralized services into truly distributed peer-to-peer systems that are not controlled by a single entity is a necessity. Relying on a few private entities to control the the content and delivery of the web is not safe nor scalable.

Plus, real-time collaborative applications are in their infancy, but I believe that in the future they will be the norm. This in itself will be a huge challenge since, in reality, the majority of the devices are poorly connected, relying on (often mobile) networks that offer little to no reliability.

Even if the underlying network is not reliable, any node should be able to perform changes in a shared data structure and, somehow, the system should be able to converge these changes into all participating nodes. Nodes should be able to enter and leave the network (either by their own will or because of network conditions), but the system should make sure that this does not lead to losing data or threatening convergence.

What protocols and data structures will allow participating users and their nodes to form ad-hoc networks for spontaneous or planned real-time collaboration without any centralized coordination?

Peer-to-peer networks can rely on special replicated data types that are distributed and conflict-free, and were built specially for these scenarios.

In this 10-minute video I show you how we can use the IPFS library and conflict-free replicated data types (CRDTs) to build a simple text editor that allows several peers to collaborate in real-time in a way that is conflict-free, supports offline use, allows nodes to come in and out of the network, but still is able to converge to a single state in all the peers.

[![https://www.youtube.com/watch?v=-kdx8rJd8rQ](https://user-images.githubusercontent.com/1211152/28122513-4cbdaabc-6716-11e7-8626-ad8154687fe1.png)](https://www.youtube.com/watch?v=-kdx8rJd8rQ)

If you're interested in this subject and / or would like to learn more, I suggest that you [head out to this repo](https://github.com/ipfs/research-CRDT), poke around in the available articles and lectures and contribute.