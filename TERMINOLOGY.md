# Terminology

the term **root document** refers to the [README document of this project](README.md), as linked
here. the term **these documents** refer to all documents referred in
[this section of the root document](README.md#contents),
in addition to the root document itself.

**InterAuth specification** refers to the specifications described within these documents.
the terms **specification** or **spec**, when used without explicitly referencing other specifications,
also refer to the same set of specifications. these terms, alongside the term **these documents**,
might be used interchangeably through-out these documents.

## Conformity

an implementation is conforming to **the specification** if and only if it satisfies all requirements
detailed in the specification, excluding those detailed in sections titled _Standard Implementation_.
satisfying requirements MUST be in accordance to requirement indicators detailed in [this section](#requirement-indicators).

### Standard Implementation

an implementation is conforming to **the standard implementation of the specification**, or
**the standard implementation of InterAuth specification**, or **standard implementation of InterAuth spec**,
if and only if it satisfies requirements detailed in the specification including those detailed
in sections titled _Standard Implementation_.

### Requirement Indicators

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
[Key words for use in RFCs to Indicate Requirement Levels](https://tools.ietf.org/html/rfc2119).
The interpretation should only be applied when the terms appear in
all capital letters.

## Common Terms

### Service

the term **service** refers to software applications residing on some
[URL](https://tools.ietf.org/html/rfc3986#section-1.1.3) accessible via the Internet, meaning its functionalities
are exposed in form of sub-paths of the root-path of the **service**, i.e. they are accessible
via some URL over the internet such that the difference between these URLs and the root URI
the **service** is said to be residing on is limited to additional
[path segment](https://tools.ietf.org/html/rfc3986#section-3.3) on the URL
attributed to the exposed functionality.

the term is to be interpreted as described only
when written in **bold** characters. the term (micro)service and microservice might be used
interchangeably and are to be interpreted as same.

### Root Address

the term **root address** of a specific **service** is used in reference to the URL the **service**
is residing on, according to the definition outlined above. the term **root-path**, or the expression
_a **service** residing on an address_,
might be used interchangeably and is to be interpreted as same.

### Endpoint

the term **endpoint** refers to some exposed functionality of some **service**. an endpoint is denoted
using the additional path segments of the endpoint URL compared to the root-path of the **service**.
for example, if a **service** resides on `https://some-server.io/some-address`, and one of its specific
endpoint is accessible via `https://some-server.io/some-address/some-namespace/some-func`, then
`/some-namespace/some-func` and `some-namespace/some-func` might be used to identify the endpoint
and refer to it.

### Signing

the term **signing** is used as an operation, conducted by some **service**, on some outgoing message,
in a manner that the receiving parties can verify that the message was signed by the **service** and it
has not been tampered with. specifics security properties are assumed for signing operations, as detailed
[here](SECURITY.md#signatures). signing is assumed between two (not-necessarily distinct) **services**,
and not in a universal manner. in other words, when the term signing is used, it is in reference to a signing
mechanism that enables safe transport of the message to a specific receiving party and not all possible
receiving parties.

the terms **signature mechanism**, **signature function**, **signing mechanism**, **signing operation**
and **signing function** might be used interchangeably and should be interpreted the same.

the terms **signed message**, **message bearing signature**, **message with signature**, etc. are used in
reference to a message that has undergone a signing operation.

### Self-Signing

the term **self-signing** is used in reference to where the signing is conducted between a **service** and
itself, i.e. messages signed through the mechanism are intended to only be verifiable by the same **service**
later (for example to ascertain that the communication is continuation of a previous message they sent).
