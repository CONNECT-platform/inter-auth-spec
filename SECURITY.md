# Security

## Cryptography

no specific cryptographic functions and/or methodologies are assumed for security of communications
specified in this protocol. it was specifically our intention that the protocols be agnostic towards
the choice of asymmetric and symmetric cryptography. all encryption is delegated to the secure communication
channels.

some properties of the cryptographic functions utilized within the protocols are assumed, specifically
for [secure communication channels](#secure-communication) and [signatures](#signatures). any implementation
MUST satisfy the required properties.

## Secure Communication

a secure communication channel between arbitrary parties within a specific **network** is assumed, i.e.
parties within the network:

- MUST be able to verify the claimed origin of an incoming message,
- MUST be able to ascertain that outgoing messages intended for specific recipients are received by said recipients
- MUST be able to ascertain that only the intended recipients of an outgoing message can obtain the contents of the message.

implementation MUST provide such mechanism between arbitrary parties, though it CAN utilize different
technologies and strategies based on parties involved.

### Standard Implementation

the standard implementation for establishing secure communication channel is utilizing Transport Security
Layer (TLS). the version will vary over time based on widespread use and known security issues. at the time
of this writing, [TLS protocol version 1.2](https://tools.ietf.org/html/rfc5246) is the standard version.
any implementation conforming to the _standard implementation of InterAuth specification_ MUST utilize
that protocol to establish secure communication channels between parties within the network.

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

since only **trusted entities** are required to establish secure external communication channels,
the specification remains explicitly agnostic about how it is implemented, as it does not affect interoperability.

## Signatures

signature mechanisms between various parties is required through out the specification. such mechanisms,
established between two parties, the _sender_ and the _receiver_, MUST satisfy the following properties:

- _receiver_ MUST be able to ascertain that an incoming message has been signed by the _sender_
- _receiver_ MUST be able to obtain the contents of incoming messages properly
- the resulting signed messages MUST be unique to _sender_ for same or varying messages

### Standard Implementation

implementations conforming to _standard implementation of InterAuth specification_ MUST conduct
all signing specified within these documents through use of shared keys of sufficient length
to sign messages and send them as [JSON Web Tokens (JWT)](https://tools.ietf.org/html/rfc7519).
choice of signature and MAC algorithms SHOULD be limited to the
[minimum requirements of the specification](https://tools.ietf.org/html/rfc7519#section-8), which at the
time of this writing would only constitute HMAC SHA-256 ("HS256").
minimum 32 bytes of full-entropy keys should be utilized, i.e. each byte should be chosen independently
of other bytes uniformly across all possible values. the shared keys MUST be unique to each pair
of communicating parties.
