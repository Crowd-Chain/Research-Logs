P2P Advantages: 

-Network operating system is not necessary 

-Cheap server cost due to users having their individual workstations 

-Less staff is needed even in larger scale projects, since the users determine which files they’ll be sharing 

-Easier to implement, compared to a server-client model, for larger scale projects 

-An issue or complete failure of one computer will not disrupt the system as a whole, the sharing and accessing is distributed between devices 

P2P Disadvantages: 

-No central back up for files 

-If a computer is accessed by many users, performance issues might occur at the computer in question 

-Lack of organization of the shared files, dependent on the organization of the owner of the file  

-Weaker security compared to alternatives; a user can spread malware/viruses disclosed as a file 

-Permissions and the integrity of the users are assumed to be without issue and bad faith, if otherwise not a relatively secure system 

 

Alternative(s) to P2P: 

Overlay Networks Overlay networks such as the Content Addressable Network (CAN),2 Chord, Pastry, and Viceroy create a virtual topology on top of the physical topology. In this sense, TTL-based P2P networks are also a type of overlay, but we use the term here to refer only to networks that create virtual topologies based on node-content attributes. Some networks, such as Chord, organize the network on the basis of each participating node’s IP address; other networks use the node’s stored data as the organizing content.  

Overlay networks share four qualities:  

• Guaranteed data retrieval  

• Provable lookup-time horizons (typically O(log N) with N being the number of network nodes)  

• Automatic load balancing  

• Self-organization  

Because overlay networks define neighbor nodes by content stored, they can change search from a standard graph-traversal problem into a localized iterative process. In this process, each hop brings the query closer to its target set of hops, which can be calculated according to a mathematical function. This reduces the overall network load and makes the query process deterministic. In abstract terms, an overlay network operates like a distributed hash table by allowing key insertion, querying, and removal. Typically, it derives those keys from the node-exposed content by, for example, using a consistent hashing algorithm such as the secure hash algorithm (SHA-1).  

An overlay network’s connectivity pattern is different from that obtained using a TTL-based algorithm in that it is structured and typically symmetrical. The structure is based on one or more mathematical functions that determine how the nodes are connected. The network’s structure contributes to the overlays’ bound lookup times. When nodes fail, overlay network algorithms provide mechanisms that let the network recover and recreate or maintain an appropriate network structure.

![overlaynetw](https://user-images.githubusercontent.com/66557091/113258036-14864d00-92d4-11eb-8f25-7088240852cd.png)
Figure 1: Sample overlay network and query's topology. 

Acquired from: DD, Doval & O'Mahony, Donal. (2003). Overlay networks: A scalable alternative for P2P. Internet Computing, IEEE. 7. 79 - 82. 10.1109/MIC.2003.1215663. 

