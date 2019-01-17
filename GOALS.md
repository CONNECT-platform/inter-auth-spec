# Goals

the goal of documents at hand is to establish a common framework enabling services to integrate with each other easily
either in a **direct** or in an **authorized** manner. why we believe that is not possible via currently available protocols
and specifications is discussed in detail in [Motivation](MOTIVATION.md) document.

to be more specific, these documents aim to establish the concept and specifications of the concept of a
**network**, composed of a specific set of **trusted entities** and services recognizing and being
recognized by those **trusted entities**, by specifying expected behaviors and communication protocols
between those services and **trusted entities**, and then specifying expected behaviors and communication
protocols of those services with each other, with the aid of those **trusted entities**, to achieve proper,
secure and seamless **direct** or **authorized** integrations.

these documents are targeted at potential implementers of such **trusted entities**, and subsequently
at developers of **provider** and **consumer** services within the **networks** defined by aforementioned
**trusted entities**.

## Interoperability

these documents aim to be highly opinionated and specific in details of the high-level APIs of those
**trusted entities** and services within the aforementioned **networks**, to achieve
maximum interoperability.

however, these documents intentionally remain agnostic about the details of lower-level communication
protocols, encryption methods, or possibly other processes that do not directly correlate to the high-level
task of establishing a **network** by implementing a set of **trusted entities** and/or developing services
within those **networks**, with the goal of increasing flexibility of the specification, specifically with
regards to security considerations, while maintaining a high interoperability within any **network**.

that might lead to limited interoperability between **networks**, for example for migrating a service
from one **network** to another, or for integrating with services residing within another **network**.
the focus of these documents is establishing and operating within the boundaries of one specific
**network**, and further work is required to achieve inter-network interoperability. the protocols in this
specification should however be easily adaptable to such future specifications in a backwards-compatible
manner and most probably by means of optional extensions, though that cannot be guaranteed for all possible
future specifications in that area.

## Security

it is a direct aim of this specification to facilitate a secure and trustable integration protocol between
services. some security properties of the **network** will be up to choice of implementations not specified
explicitly by these documents, however, assuming properties described in [this section](#SECURITY.md), the
protocols should have following properties:

- strong backward and forward secrecy
- resilience against MITM
- resilience against replay attacks
- resilience against untrusted services

as mentioned in the [previous section](#interoperability), the specification is agnostic to lower
level security measures in communication between all involved parties, however it explicitly specifies some
properties that must be satisfied by any choice of the aforementioned measures, and it does make specific
recommendations for such choices according to the technologies available at the time of this writing.

## Seamlessness

it was a main goal of this specification to be as easy and as transparent as possible for developers, both
implementers the **trusted entities** of a network and implementers of **provider** and **consumer** services,
prioritizing the latter over the former. the specification aims to encourage higher levels of integrations,
which in turn might lead to higher adoption of micro-service architectural styles and in turn even further integration
between these services, through lowering implementation costs without sacrificing security and robustness
of communication protocols.

the specification also aims at encouraging reuse of services developed by independent entities within the
**network**, by means of lowering implementation costs for both **providers** and **consumers**, and also
lowering necessary trust required between two independent parties for such integrations, by delegating
as much of the required trust to **trusted entities** of the **network**. it is highly recommended for
implementers of any **network** according to this specification to also implement any complementary such service
in addition to **trusted entities** specified in these documents, for example ones for measuring performance
and reliability of **provider** services.
