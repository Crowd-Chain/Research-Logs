# Log

TODO:
* Details of LDP implementation
* Modification to device location services (Geospoofing)
* TBI (Misreports, User spoofing, Metadata spoofing)

### 1-8 April 2021:

**Blind Reports:**

A few weeks ago during a meeting we noted that the most crucial task at this time is figuring out a method to determine whether or not a report is "honest".
State-of-the-art news checkers are built on "factual databases", see [AI Blockchain Platform for Trusting News by Zonyin Shae et al](https://www.semanticscholar.org/paper/AI-Blockchain-Platform-for-Trusting-News-Shae-Tsai/c510a97a1f1909ea59b0458e1689224be0887dfd), to be able identify ideal "honest" reports. Yet these systems depend on
* external information
* semantic information
* metadata
which are outside of our scope. What we needed was something which could work on generic event reports, with minimal data. 

During another meeting, I thought of how [Double-Blinded Trials](https://en.wikipedia.org/wiki/Blinded_experiment#Double-blind_trials) are frequently conducted in medical research, where external validators are limited. If we were **indepently** receiving reports of a similar event in a similar proximity within a similar timeframe, **before the events** were actually visible on the system, the reported event would be considerably more believable.

**Zero-Knowledge Proofs:**

To achieve "blind"ness I investigated ZK Proofs. A ZK Proof could be used to "blind" a report by encrypting a report code (ex. 1201) and a concatanted discrete geo-region (ex. N38E27-N39E28). If two or three people within the same geo-region give the same report code, we will be able to match them although the report code and location itself are invisible.

While both [bulletproofs](https://www.youtube.com/watch?v=Adrh6BCc_Ao) and [range proofs](https://github.com/ing-bank/zkrp) have properties which would allow us to "blind" reports, there are two major drawbacks:

1. "Unblind"ing a report after validation is non-trivial. ZK Proofs are employed to prove something is known and to only **demonstrate** that the thing is known. They are, by virtue of design,  meant to not expose the value or state of the thing. Thus if we do get a ZK match, we will then have to requery reports from somewhere else. This might be stored and found in a private database invisible from users. Or the client might be informed that their report was validated, and asked to "pass on" the actual report from their device now that the gate has been opened. This is a tedious and redunndant process, but it _should_ be solvable.
2. Seeming inability to satisfy the soundness property. Any ZK Proof is required to satisfty the property that "if the statement is false, no cheating prover can convince the honest verifier that it is true, except with some small probability". Yet, this model _is_ decievable in all likelihood. Consider how a spammer might use multiple devices to report the same false event from inside the same geo-location. Thus if multiple cheating provers collude, they can successly deceive the system.

While I ended up reaching a dead-end here, I noted something interesting. ZK Proofs are generally meant as a dialogue betweeen a client and verifier, yet in our problem we have multiple clients. Then could it be possible to take advantage of a new variable introduced from having multiple clients to validate, instead of just one? 

**Time-Attacking:**

A single reporter only exists in a place, but multiple reporters exist at a distance from one another. Not just in space, but in time.

Consider a fire. The first people in its proximity will be the first to see it, hopefully also the first to report it. Yet it is very unlikely that everyone will reach for their phone at the same time and call the fire department. Invariably they will all have different response times. If anything, if two people report a particular disaster (report code) at nearly the same time (seconds or miliseconds apart) it might be possible that these are two seperate events co-occuring.

Then this distance between reports, especially temporal distance, can help us with relating and differentiating events to and from one another. From here on out, we will be looking into unsupervised learning techniques...

**Network Architecture:**

Because timestamps are generated server-side, factoring in this timestamp will require us to centralize the Crowdie network (which might warrant a name change). So instead of a peer-to-peer network, it will be a master-worker relationship. Our reports protocol is already designed to be usable by independent services, but the question of whether or not there can be multiple "news hubs" in the network, is outside the scope of what we wish to achieve by the final demo of this project.

### 31 March 2021:
Read through geospatial techniques in LDP:
* [Local Differential Privacy on Metric Spaces: optimizing the trade-off with utility](https://ieeexplore.ieee.org/abstract/document/8429310?casa_token=O8AToF7tGy0AAAAA:uQtYMM1a_Btksx8yR9Yi8ehB8mCxAmCfUjUbUPiMln-EtrmC2m20z06XxX1ky1R4lQ1HkMKGqi4)
* [Location Guard](https://github.com/chatziko/location-guard)
* [Geo-Indistinguishability: Differential Privacy for Location-Based Systems](https://arxiv.org/abs/1212.1984)

### 22 March - 30 March 2021: 
Investigated what data could be spoofed:
* Geospoofing: 
  * A malicious user could fake their coordinates. 
  * At this time we ask for device coordinates "locally" and will have clientside code apply Local Differential Privacy to skew an individual user's coordinates.
  * But there isn't much stopping a user from modifying the clientside code or device location services.
    * We can use a checksum to compare the user's clientside code to the latest version. **This should be implemented in the future.**
    * But the question of how to check if device location services have been modified still remains unanswered.
* Time spoofing:
  * A malicious or unsuspecting user could falsely report their time.
  * **Working Solution: Generate a timestamp on the serverside at the time of reporting.**
* Report spoofing:
  * A malicious or unsuspecting user could falsely report an event that isn't occuring.
  * **Proposed Solution: "Blind Reports"**
    * Reports aren't made visible immediately. Instead they are first sent to another table where users have write access only.
    * During a grace period, if similar/identical event reports are reported in the BLIND table, they are pushed to the reports table where they become visible.
    * If a report is not blindly validated in this manner, it will still be sent to the reports table after a few hours. The report will have been recorded, but not shown at the time of occurence.
* Misreports:
  * Assume there is an ongoing event, but the user reports something else.
  * Could *possibly* be integrated into the "Blind Reports" solution.
  * **To be further investigated.**
* User spoofing:
  * Reports do not carry any information besides user coordinates at this time.
  * *Can a reporter fake another reporter?* 
  * Mark by UUID? User accounts?
  * PoW Blockchain? (Very costly)
  * **To be further investigated.**
* Metadata spoofing:
  * Reports do not carry any metadata payload at this time.
  * **To be further investigated.**
