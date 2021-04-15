# Research Logs

**Our Issues with Crowd-Sourced Reporting**

* False Reporting
* False location sharing
* VPN usage
* Spamming reports

## Papers

### A new approach to crowd journalism using a blockchain-based infrastructure (Leonardo Teixeira, Ivone Amorim, Alexandre Ulisses Silva)

"Permissioned blockchain: "The intrinsic configuration of such blockchains controls the participants' transactions and defines their roles in which each participant can access and contribute to the blockchain. Maintain an access control layer to allow certain actions to be performed only by certain identifiable participants.		They are crafted to take advantage of blockchains without sacrificing the authority aspect of a centralized system."

"Proof ofWork (PoW) is the lottery-based algorithm used by the Bitcoin blockchain network and it is based on the premise that a node must use computational power to prove that it has no malicious intent to tamper with the network. On the other hand, the Proof of Stake (PoS) stands out for its absence of complicated and expensive calculations. This method states that participants who have more digital assets of the cryptocurrency would be less likely to act maliciously on the network and so they are more likely to be chosen to forge the new block. Along with these two, there are many other lottery-based algorithms to define a network consensus (Proof of Authority (PoA), Proof of Elapsed Time (PoET), Proof of Burn (PoB), etc.)."

### Contributions to our project
* 

### AI Blockchain Platform for Trusting News(Zonyin Shae, Jeffrey J.P. Tsai)


"In our model as shown in Figure 4, the news propagates among news consumers (general population), social media, and press media. Each news propagate from one entity to other entity will be recorded as a transaction in the blockchain ledger."

"Our system model consists a “factual database” as a root of blockchain data architecture for us to trace back during the process of analyzing, tracing, and ranking the news. This factual database, in which all records are considered factual, provides the ground truth and corner stone for our system. News in the Internet will be divided into two groups: one group is able to trace back to the factual database in the news blockchain supply chain graph, and the other group cannot
(that is, this group can only be traced back into some unverified news data sources)."
	
"The factual database needs to be built from all the factual news. This is a critically important and quite a challenging task. We propose that, at the beginning, the database only consists of the facts which we can take it for granted as fact in nature and do not need any tool or person to verify. Some of the factual news data sources that we currently consider are, for examples, the library of speech records of law makers, and the official speech records of presidents and public figures.
The information in these public records considered above should have been officially validated as facts and can be used to provide a basis of ground truth of facts."

"If the news is verified to be factual, then it can be added into the factual database as well."

![AINews](https://user-images.githubusercontent.com/54986089/113020136-f95bf600-918a-11eb-91f0-4af35d5ae35d.PNG)


### Overlay Networks: A Scalable Alternative for P2P(Diego Doval and Donal O’Mahony • Trinity College Dublin)

"This example underscores the problems of flooding-style P2P networks. Even though only Nr can answer the query, all the nodes within TTLrange must process it. Also, if the value had been stored in node Nar the query result would not be found unless the message’s TTL was set to a higher value, potentially flooding the entire network."

"In Freenet, the query is forwarded according to a more sophisticated cachebased routing strategy, and the result returns through the request’s exact node-to-node path, therefore guaranteeing local anonymity"

"Networks such as Gnutella organize nodes independently of the underlying physical topology; neighbors might exist within the same subnetwork or across the Internet."

"Although some networks adapt to the underlying physical topology, such optimization is not required for the algorithm to operate properly. These networks are unstructured: nodes attach to the network according to measures unrelated to content, such as join-order, connection speed, and even physical proximity, creating a random connection topology.
.Content location and network topology are uncorrelated.
.The network is random(theoretical limit of N hops)"

"All content must therefore be “reachable” by the content-location service, network load must be constrained, and search times must be bound by a predictable limit to avoid arbitrary reply times. In other words, search must be deterministic."

"Chord: organize the network on the basis of each participating node’s IP address * other networks use the node’s stored data as the organizing content *"

"In abstract terms, an overlay network operates like a distributed hash table by allowing key insertion, querying, and removal. Typically, it derives those keys
	from the node-exposed content by, for example, using a consistent hashing algorithm such as the secure hash algorithm"

"When nodes fail, overlay network algorithms provide mechanisms that let the network recover and recreate or maintain an appropriate network structure."

"Lookup data on the basis of identifiers derived from the content, and thus don’t directly support keyword-based searching."
