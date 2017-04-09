# A Note on Our Consensus Protocol
In this note, we briefly discuss the consensus protocol in our system. 
Our consensus protocol is inspired by [HydraChain](https://github.com/HydraChain/hydrachain/blob/master/hc_consensus_explained.md). 
To strengthen the resistance to Byzantine faults, **one additional phase that prevents premature commitment is added to HydraChain 
before a block can be committed**. Specifically, in HydraChain, a block can be committed immediately by a node once the node 
intercepts a quorum for the block. Such a commitment might be premature and leads to a fork. The newly added phase is thus invoked 
after a node intercepts a quorum. The resulting protocol is then **PBFT-like**, and this newly added phase serves the same purpose 
as the Commit phase in PBFT. 

Note that HydraChain is inspired by [Tendermint](https://github.com/tendermint/tendermint), a PBFT-like consensus protocol. 
Indeed, one can deem HydraChain as a simplification of Tendermint. Hence, the demand to add one more phase to HydryChain inevitably 
steers our focus to Tendermint. We hence decide to adopt Tendermint as our consensus protocol as it embodies the additional phase 
that we need to prevent premature commitment.
