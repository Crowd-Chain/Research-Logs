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

The emergence of citizen journalism has prompted the journalism field and scholars to readdress what constitutes journalism and who is a journalist. Citizen journalists have disrupted news-media ecosystems by challenging the veracity and representativeness of information flowing from mainstream news-media newsrooms. However, the controversy related to the desired level of citizen involvement in the news process is a historical debate that began before the citizen-journalism phenomenon. As early as the 1920s, journalist and political commentator Walter Lippman and American philosopher John Dewey debated the role of journalism in democracy, including the extent that the public should participate in the news-gathering and production processes.  

This questioning of citizen involvement in news reemerged as an issue with the citizen journalism phenomenon around the late 1990s. People with no news-media organizational ties have taken advantage of the convenience and low cost of social computing technologies by publishing their own stories and content. These people are referred to as citizen journalists. Scholars have assessed the quality and credibility of citizen-journalism content, finding that citizen journalists have performed well on several standards of traditional news-content quality. Levels of quality differ dependent upon citizen journalists’ goals and motivations, such as serving the public interest, increasing self-status, or expressing their creative selves. 


 <img width="639" alt="Screen Shot 2021-04-01 at 16 50 05" src="https://user-images.githubusercontent.com/66557091/113304402-ad37bf80-930a-11eb-9b53-051f1e840484.png">
Figure 2: Example formal definitions for citizen (crowd) journalism 

Acquired from: Miller - Carpenter, Serena. (2019). Citizen Journalism. 10.1093/acrefore/9780190228613.013.786. 

Benefits of crowdsourcing: knowledge discovery, peer learning, and deliberation Through crowdsourcing, journalists have access to a larger number of people than ever before. The online crowd is a huge potential source pool for the journalist with the size of the participant 18_Franklin & Eldridge II,eds_Ch-18.indd 188 6/20/2016 5:07:33 PM T&F Proofs, Not for Distribution Crowdsourcing in open journalism 189 crowd, in theory, being almost limitless. In practice, limited access to the Internet, language, and skill barriers make the process accessible only to a certain number of people. It is also limited in terms of the number of people who have knowledge about the open journalistic process and can thus participate.  

Using crowdsourcing, journalists can tap into the collective intelligence of the crowds and channel that to their articles. The larger the number of participants, the more likely the journalist is to find useful information. Crowdsourcing hence supports knowledge search in journalism. Empirical studies show that crowdsourcing in journalism can bring in relevant information that helps journalists to proceed with their investigations and that the crowdsourced knowledge search can lead to a fast knowledge discovery and even to a discovery of knowledge that the journalist did not know to search for 

Acquired from: Aitamurto, Tanja. (2017). Crowdsourcing in Open Journalism: Benefits, Challenges and Value Creation. 10.4324/9781315713793-19.
