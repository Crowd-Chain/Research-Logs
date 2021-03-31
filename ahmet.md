# Log

TODO:
* Details of LDP implementation
* How to do Blind Reports (in the light of peer-to-peer research from group members)
* Modification to device location services (Geospoofing)
* TBI (Misreports, User spoofing, Metadata spoofing)

### 1 April 2021:

### 31 March 2021:
Read through geospatial techniques in LDP:
* [Local Differential Privacy on Metric Spaces: optimizing the trade-off with utility](https://ieeexplore.ieee.org/abstract/document/8429310?casa_token=O8AToF7tGy0AAAAA:uQtYMM1a_Btksx8yR9Yi8ehB8mCxAmCfUjUbUPiMln-EtrmC2m20z06XxX1ky1R4lQ1HkMKGqi4)
* [Location Guard](https://github.com/chatziko/location-guard)

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
