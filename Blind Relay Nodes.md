Makes use of [[Quality of Service]], [[Public & Private Compute]], [[Private Peers]].

The idea of blind relay nodes is that other than some meta data about where packages are to be routed to, they can't see the content that is being transferred.  Most of the internet already works in this way, assuming you are using an encrypted transport such as TLS.

The relay nodes referred to here would be an [Application level protocol](https://en.wikipedia.org/wiki/Application_layer), with intelligence specific to how messages should be routed, and potentially stored, within this peer to peer network.  This may include fee-based services, where nodes incur a cost but are compensated for that by users.

Certainly, relay nodes should offer the capability of temporary storage should the destination node be offline.  How long is a reasonable time frame to store messages for?  That may vary based on the policy of the node, and the compensation offered by the user.

Various strategies can be used to anonomize a user sending messages to relay nodes:

* using a throw away identity
* using random/different relay nodes for each "chunk" of a message
* using trusted peers as relay nodes
* using relay networks purpose designed for privacy

