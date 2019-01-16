# Goals

the goal of documents at hand is to establish a common framework enabling services to integrate with each other easily
either in a **direct** or in an **authorized** manner. why we believe that is not possible via currently available protocols
and specifications is discussed in detail in [Motivation](MOTIVATION.md) document.

## Security

as InterAuth specification aims to be utilized by a vast number of possibly small **provider** and **consumer** services,
it aims to be extremely secure and future-proof. the goal is for the security to stem from the protocol design instead of
implementational details, for example encryption functions, such that the totality of the protocol remains secure and
worst-case scenarios can be handled by updates isolated to cryptographic specifications of any implementation.

secure communication channels between arbitrary parties, though assumed to be present, ARE NOT RELIED ON. the specification does not necessitate any specific protocol for such channels, although the most widespread and secure of such protocols,
which at the time of this writing would be [TLS protocol version 1.2](https://tools.ietf.org/html/rfc5246), should be
utilized for all message passing described in the specification. secure communication channels between arbitrary parties and specific parties ARE RELIED ON occasionally. 

no specific encryption mechanisms are assumed for communications according to described protocols. encryption of communications is generally NOT RELIED ON, except possibly for secure communication channels with specific parties.
however, the specifics of those encryptions are left up to the specifics of establishing aforementioned secure communication
channels. the protocols are specifically designed to NOT RELY ON any form of asymmetric encryption, as their security is not
percieved as future-proof.

## Interoperability

## Ease of Development

## Automatibility

## Shareability
