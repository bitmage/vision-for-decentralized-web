[[Private Data]]

# Git

How is git wire protocol defined?

* https://github.com/git/git/blob/master/Documentation/technical/protocol-v2.txt

# Flatbuffers

[flatbuffers docs](https://google.github.io/flatbuffers/)
[flatbuffers in Rust](https://docs.rs/flatbuffers/0.6.0/flatbuffers/)
[flexbuffers in JS](https://github.com/google/flatbuffers/pull/5973/files)

# Capn Proto

[port to javascript stalled](https://groups.google.com/g/capnproto/c/lESKRE_pix8/m/jX59zEUXBgAJ?pli=1)

# Why define our own protocol?

[Redis Protocol](https://redis.io/topics/protocol) for comparison, satisfies many of the principles that we want.  But implementing using Flatbuffers I feel will make it more accessible for others who want to follow our implementation in other languages.

# GraphQL

GraphQL looks really promising given recent improvements.  [Project Constellation](https://www.youtube.com/watch?v=MvHzOwdLb_o) was implemented, which resulted in the [Supergraph](https://www.apollographql.com/docs/intro/platform) which is implemented efficiently in the Rust-based [Router](https://www.apollographql.com/docs/router/).  It seems the Router can run at [~115 mb of memory consumption even with a 7000 line schema](https://github.com/apollographql/router/issues/1466) and [latencies are very low](https://www.apollographql.com/blog/announcement/backend/apollo-router-our-graphql-federation-runtime-in-rust/).

[Juniper](https://github.com/graphql-rust/juniper) is a GraphQL server written in Rust.  It supports [subscriptions](https://graphql-rust.github.io/juniper/master/advanced/subscriptions.html).  Apollo Federation protocol (including the Router implementation) [does not currently support subscriptions](https://www.apollographql.com/docs/federation/).  So we would be using a request/response lifecycle with the supergraph, while dropping down to the individual service for any subscriptions.  I think I can live with that.  It's a way better story, further implemented than anything else I've looked at.

This [schema registry](https://github.com/pipedrive/graphql-schema-registry) looks like a great way to manage microservice contracts.

# Cross Platform Business Logic

Could we wrap FlatBuffers in a validation and query language that can be implemented in a number of different target languages?

Or alternatively, implement the query language within Rust, and embed a Rust binary that performs validation and querying.