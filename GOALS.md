# Goals

these documents aim to establish the concept and specifications of a
**network**, composed of a specific set of **trusted entities** and **services** recognizing and being
recognized by those **trusted entities**, by specifying expected behaviors and communication protocols
between those **services** and **trusted entities**, and then specifying expected behaviors and communication
protocols of those **services** with each other, with the aid of those **trusted entities**, to achieve proper,
secure and seamless **direct** or **authorized** integrations.

these documents are targeted at potential implementers of such **trusted entities**, and subsequently
at developers of **provider** and **consumer services** within the **networks** defined by aforementioned
**trusted entities**.

## Interoperability

these documents aim to be highly opinionated and specific in details of the high-level APIs of those
**trusted entities** and **services** within the aforementioned **networks**, to achieve
high levels of interoperability within any such **network**.

## Flexibility

these documents intentionally remain agnostic about the details of lower-level communication
protocols, encryption methods, or possibly other side processes, with the goal of increasing flexibility of the specification, specifically with regards to security considerations, while maintaining a high interoperability within any **network**.

wherever the said ambiguity affects inter-**network** interoperability, a _standard implementation_
is also specified. the specification, constrained strictly to the _standard implementation_, i.e. the
**standard implementation of InterAuth specification**, should also guarantee inter-**network** interoperability.
non-standard implementations should still guarantee interoperability within a **network**.

## Security

it is a direct aim of this specification to facilitate a secure and trustable integration protocol between
**services**. some security properties of the **network** will be up to choice of implementations not specified
explicitly by these documents, however, assuming properties described in [this section](#SECURITY.md), the
specification aims to achieve following properties:

- strong backward and forward secrecy
- resilience against MITM
- resilience against replay attacks
- resilience against untrusted services

## Seamlessness

it was a main goal of this specification to be as easy and as transparent as possible for developers, both
implementers the **trusted entities** of a network and implementers of **provider** and **consumer services**,
prioritizing the latter over the former. the specification aims to encourage higher levels of integrations through lowering implementation costs without sacrificing security and robustness
of communication protocols.

## Stateless-ness

stateless implementations of **servicess** conforming to this specification should be possible, except in case of **trusted entities**. full stateless conforming implementations might not be able to achieve the best performance, however it should be possible to mitigate all such performance penalty through use of caching mechanisms, without requiring any long-term persistence on conforming **services**.

## Reusability

the specification also aims at encouraging reuse of **services** developed by independent entities within the
**network**, by means of lowering implementation costs for both **providers** and **consumers**, and also
lowering necessary trust required between two independent parties for such integrations, by delegating
as much of the required trust to **trusted entities** of the **network**. it is highly recommended for
implementers of any **network** according to this specification to also implement any complementary such **service**
in addition to **trusted entities** specified in these documents, for example ones for measuring performance
and reliability of **provider services**.
