Makes use of [[Public Ledger]].

Services which today rely upon a centralized server don't need Peer Discovery, because all the peers check in with a known host such as Facebook.com.

There are various reasons we may want to operate without the need for such a central host, such as privacy, anti-censorship, or because the host may be unavailable due to network disruptions.  In this case we need some other way of finding each other on the network.

Peer Discovery algorithms were designed for this purpose.  We may use different methods depending on whether we are discovering peers on a local network, a mesh network, or across the internet.  A key question is how do we find our peers without knocking on every door?  Also, how do we propogate knowledge of peers without knocking on every door?

One of the simplest and most versatile peer discovery methods uses a [[Distributed Hash Table]].  This can be combined with:

* a bootstrapping server at a known address, which knows about many peers
* a bootstrap list, which may be contained in a downloaded file, a QR code, or transferred from one peer to another

The [SWIM protocol developed by Uber](https://www.cs.cornell.edu/projects/Quicksilver/public_pdfs/SWIM.pdf) was developed as an efficient peer to peer membership tracker.  This may be useful to read about, and perhaps a suitable implementation is available and ready to use.