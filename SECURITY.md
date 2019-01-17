# Security

## Secure Communication

a secure communication channel between arbitrary services within a specific **network** is assumed.
it is highly recommended that the most common and secure method for establishing such communication channels
be used, which at the time of this writing would be
[TLS protocol version 1.2](https://tools.ietf.org/html/rfc5246).

however, the protocols are intended to not be tied to specifics of establishing such communication,
and alternatives are considered and discussed in case of a failure in that layer, though that
should not be considered as part of the main body of the specification, and should be utilized with
extreme caution and consideration as it is highly recommended for most scenarios to stick to standard
methodologies for establishing secure communication instead of utilizing customized methods within
established **networks**.

### External Communication

a secure communication channel between **trusted entities** of the **network** and external parties
is assumed. specifically, **trusted entities** are assumed to be able to establish secure communication
channels with end-users, depending on how end-users are identified in the **network**, in a manner that
guarantees an acceptable level of certainty that the intended user was communicated with.

a recommended method for establishing such communication channels is utilizing mechanisms such as E-Mails,
SMS, or verified authenticator apps on user's devices. such mechanisms can be used to send a time-based
**self-signed** token by the **trusted entity** to the user, which on top of traditional methods for
establishing secure communication channels (such as TLS/SSL) can be utilized to establish communication
with the user to a reasonable degree of certainty that the intended user was communicated with.

## Cryptography

no specific cryptographic functions and/or methodologies are assumed for security of communications
specified in this protocol. it was specifically our intention that the protocols be agnostic towards
the choice of asymmetric and symmetric cryptography. all encryption is delegated to the secure communication
channels, to ensure the protocol is future-proof in light of foreseeable changes in Quantum Computing.

## Signatures

TO BE COMPLETED
