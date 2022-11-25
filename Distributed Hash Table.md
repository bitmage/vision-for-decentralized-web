Created On: [[2022-10-22]] 

A DHT can be used for [[Peer Discovery]] and also can be used to implement a distributed database, allowing for [[Encrypted Storage as a Service]].  A DHT may also be a useful foundation for a [[Public Ledger]], for message propagation, and for data redundancy.

The core idea behind a DHT is that a hashing algorithm is used on each piece of content to be stored.  We then "slice the pie" giving each available node an equally sized address range.  Whatever hash our content ends up with, the appropriate node will be selected to store it.  The address space can also be repeated multiple times over the set of nodes, creating data redundancy for resilience and access speed.

![Riak Ring](https://docs.riak.com/images/riak-ring.png)

[BitTorrent is implemented using a DHT](https://www.maketecheasier.com/how-bittorrent-dht-peer-discovery-works/).  [[Holochain]] also [uses a DHT](https://developer.holochain.org/concepts/4_dht/).  Riak [distributes data amongst its nodes using a DHT](https://docs.riak.com/riak/kv/2.2.3/learn/concepts/clusters.1.html).

Wikipedia lists [other applications that use DHTs](https://en.wikipedia.org/wiki/Distributed_hash_table#Examples).

Notably, [IPFS](https://ipfs.tech/) may be a suitable building block for data storage, either public or encrypted.

