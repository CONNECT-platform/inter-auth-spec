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

### Secure Communication Channel

a secure communication channel between arbitrary parties within a specific **network** is assumed.
it is highly recommended that the most common and secure method for establishing such communication channels
be used, which at the time of this writing would be
[TLS protocol version 1.2](https://tools.ietf.org/html/rfc5246).

however, the protocols are intended to not be tied to specifics of establishing such communication,
and alternatives are considered and discussed in case of a failure in that layer, though that
should not be considered as part of the main body of the specification.

### Cryptography

no specific cryptographic functions and/or methodologies are assumed for security of communications
specified in this protocol. it was specifically our intention that the protocols be agnostic towards
the choice of asymmetric and symmetric cryptography. all encryption is delegated to the secure communication
channels, and for the protocols only digital signatures are assumed with explicitly mentioned
expected properties. the specification is agnostic to any properties beyond those explicitly mentioned.


## Ease of Development

## Automatibility

## Shareability
