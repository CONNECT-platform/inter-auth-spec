# Motivation

## Direct Integration

as it currently stands, the conventional method of conducting **direct integration**, which can be thoguht of as a mere _authentication_ of the **consumer** by the **provider**, is for the developers of the **consumer** service to utilize some web-portal or some other provider-specific method to first _authenticate_ themselves (usually by registering real accounts), obtaining some sort of _API key_, adding (installing or effectively developing) some form of _SDK_ (software development kit) for working with the APIs of the **provider** on their **consumer** service, and feeding the retrieved _API key_ into the _SDK_. this obviously has the following down-sides:

1. _API keys_ are bound to accounts and not **consumer** services. in-effect, developers are authenticated and subsequently offered these keys, and in many cases multiple **consumer** services belonging to the same entity (team/organization) will end-up sharing _API keys_. this alone cause its own host of issues:
    1. developers can leak out _API keys_ (for example in case of an ungraceful dispute with the owner organization)
    1. developers working on one **consumer** service can inadvarently affect services provided by the **provider**, partially or totally breaking functionality of some other **consumer** service.
    1. developers cannot readily distinguish the usage of their **consumer** services.
1. the _API key_ usually is the only security measure in-place. in case of a MITM attack (for example, an occasional failure of the TLS/SSL layer between **consumer** and **provider**), all forms of secrecy in the protocol is lost.
1. the process is extremely tedious and unstandardized.

additionally, in most cases that involve some financial transaction in exchange for provided services, the cost for the **consumer** would be tied in some way to the number of _API calls_ they make to the the **provider**, for calculating which they should also completely rely on the truthfulness of the **provider**. even in case of truthful providers, this will at least affect the incentives of the providers to maintain and/or improve the quality and reliability of their usage measurement mechanisms. this would also in-turn fallback on the credibility of the provider entity, increasing the entry barrier for service providers to be able to offer services feasibly in the market.

## Authorized Integration

currently there aren't many **authorized integration**, which can be thought of as _authorization_ of **consumer**'s access to specific resource/services offered by the **provider**, is also not well supported by standing specifications, frameworks, protocols, etc. currently most widely adopted and actively maintained framework for inter-service authorization is OAuth 2.0 (since OpenID is also utilizing OAuth 2.0 at the time of this writing, it will not be referenced here specifically). however:

1. [OAuth 2.0 has limited interoperability](https://tools.ietf.org/html/rfc6749#section-1.8), which might result in non-interoperable implementations by various **provider**s. this means manual effort is required on part of developers **consumer** services per **provider** for implementing proper **authorized integration**s.
1. OAuth 2.0 is designed focusing on end-user authorization, relying extensively on concepts specific to that scenario, such as user-agents and [HTTP redirects](https://tools.ietf.org/html/rfc6749#section-1.7), which limit its applicability in the domain of authorized integrations (for example, in case of systematic **authorize**ing parties, where all of the communication should occur without involvement of any user-agent).
1. OAuth 2.0 does also on average require sizable investment of time and funds for developers of **provider** services to implement, as the specification leaves quite a lot of the design and specifics of the final implementation up to implementers, in exchange for being highly-extensible. this in turn discourages **provider** service developers from providing **authorized integration**s, limiting availability of such integrations in general.
1. there are ongoing discussions about security and robustness of OAuth 2.0. there are [arguments by some of the original authors of OAuth2.0 on the aforementioned issues](https://hueniverse.com/oauth-2-0-and-the-road-to-hell-8eec45921529), which might make it less than ideal for adoption by a large number of (micro)services.
