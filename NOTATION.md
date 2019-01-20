# Notation

_TODO_: this is a proper sample of the syntax. the notation of this syntax should be explained in this section.

```
(1) C -> DIM [/token]: {
  request: {
    consumer: <consumer-URL>,
    provider: <provider-URL>,
    endpoints?: [<requested-endpoints>],
    meta?: <meta object>,
    selfref: <nonce>_[C -> C]
  }_[C -> DIM]
}

(2.a) DIM -> C (1): [403] not recognized

(2.b) DIM -> C (1): [403] {
  rejection: {
    signature_match: < true | false >,
    consumer_match: < true | false >,
  }_[DIM -> C]
}

(2.c) DIM -> C (1): [404] {
  rejection: {
    provider_match: false
  }_[DIM -> C]
}

(2.d) DIM -> P [/iauth/approve]: {
  verification: {
    consumer: <consumer-URL>,
    endpoints?: [<requested-endpoints>],
    meta?: <meta object>,
  }_[DIM -> P],
  request: <(1).request>
}

(3.a) P -> DIM (2.d): [403] {
  rejection: {
    request: <(2.d).request>,
    consumer: <(2.d).verification.consumer>,
    reason?: <reason>
  }_[P -> DIM]
}

(3.b) P -> DIM (2.d): [200] {
  verification: {
    token: {
      consumer: <consumer URL>,
      endpoints?: [<requested endpoints>],
      meta?: <meta object>,
      expires_in: <expiry date>
    }_[P -> P],
    request: <(2.d).request>
  }_[P -> DIM]
}

(4.a) DIM -> C (1) | (3.a): [403] {
  verification: {
    token: {
      
    }
  }_[DIM -> C]
}
```
