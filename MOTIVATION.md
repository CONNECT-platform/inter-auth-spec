# Motivation

## Background

integration between different **services** is dependent on **services** being able to establish communication criteria
and then subsequently communicating based on the established criteria. stanrdization of _API_ or _API documentation_ has availed solutions such as _automatic SDK generation_ to support the second component. however, the first component still suffers from lack of any standardization, as there are either no specifications available or available specifications lack proper applicability as they have been designed with other intentions.

## Direct Integration

as it currently stands, the conventional method of conducting **direct integration**, is for the developers of the **consumer service** to utilize some web-portal or some other provider-specific method to first _authenticate_ themselves (usually by registering real accounts), obtaining some sort of _API key_, and feeding that _API key_ into the *SDKs* they utilize to communicate with **provider** APIs.

this method involves authenticating accounts bound to developer/maintainers of **consumer services** instead of the **services** themselves, and these maintainers might use the same authentication credentials (_API key_) for a multitude of their **services**. subsequently, it bears several issues:

1. there is no isolation in communication criteria of different **consumer services**, for example usage limits, allocated resources, etc. this can for example cause developers of one **consumer service** inadvarently breaking functionality of another **service** sharing the _API key_.
1. *API keys* are granted towards people, which are not necessarily bound to a specific **consumer** **service** for all of its lifetime, partially delegating the security of the *API keys* to HR processes within the larger maintainer entity. occasionally **provider services** do offer work-arounds for this issue, however that translates into increased development and maintenance costs for developers of **provider services**.
1. the current method is by no means interoperable, which translates into higher costs for developer/maintainers of **consumer services**.

additionally, in most cases that involve some financial transaction in exchange for provided services, the cost for the **consumer** would be tied in some way to the number of _API calls_ they make to the the **provider**, for calculating which they should also completely rely on the truthfulness of the **provider**. even in case of truthful providers, this will at least affect the incentives of the providers to maintain and/or improve the quality and reliability of their usage measurement mechanisms. this would also in-turn fallback on the credibility of the provider entity, increasing the entry barrier for service providers to be able to offer services feasibly in the market.

## Authorized Integration

as it currently stands, the main actively maintained specification that might be applied for **authorized integration** is OAuth 2.0 (since OpenID is also utilizing OAuth 2.0 at the time of this writing, it will not be referenced here specifically). however:

1. [OAuth 2.0 has limited interoperability](https://tools.ietf.org/html/rfc6749#section-1.8), which results in non-interoperable implementations by various **providers**.
1. OAuth 2.0 is designed focusing on end-user authorization, relying extensively on concepts specific to that scenario, such as user-agents and [HTTP redirects](https://tools.ietf.org/html/rfc6749#section-1.7), which limit its applicability, for example, in case of systematic authorizing parties, where all of the communication should occur without involvement of any user-agent, or in cases where the authorization is not (at least immediately) initiated by the authorizing parties, with limited to no availability of any user-agent.
1. OAuth 2.0 does also on average require sizable time investment for developers of **provider services** to implement, as the specification leaves sizable portions of the design and specifics of the final implementation up to implementers, in exchange for being highly-extensible. this in turn discourages **provider service** developers from providing **authorized integrations**, limiting availability of such integrations in general.
