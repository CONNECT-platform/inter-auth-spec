# inter-auth-spec

these documents aim to provide a framework for seamless and secure communication between various (micro)services in various scenarios. more specifically, these documents aim to provide a framework for facilitating authentication and authorization between such (micro)services, in a secure and easy to implement manner.

to be more specific, these documents focus on one service, **consumer**, requesting some functionality or data from another service, **provider**, with them most probably being developed and maintained by separate entities, and probably some financial mechanism required to provide services of the **provider**. this scenario can be broken into two categories:

1. where the functionality/data provided by the **provider** merely relates to the **consumer**, or by some other measure the **provider** can and will provide the aforementioned functionality/data to the **provider** without authorization of any third-party being required

1. where the functionality/data provided by the **provider** relates to, or by some other measure requires approval of a third-party, the **authorizer**

## status quo

as it currently stands, the conventional method of conducting the first category integration, which can be thoguht of as a mere _authentication_ of the **consumer** by the **provider**, is for the developers of the **consumer** service to utilize some web-portal or some other provider-specific method to first _authenticate_ themselves (usually by registering real accounts), obtaining some sort of _API key_, adding (installing or effectively developing) some form of _SDK_ (software development kit) for working with the APIs of the **provider** on their **consumer** service, and feeding the retrieved _API key_ into the _SDK_. this obviously has the following down-sides:

1. _API keys_ are bound to accounts and not **consumer** services. in-effect, developers are authenticated and subsequently offered these keys, and in many cases multiple **consumer** services belonging to the same entity (team/organization) will end-up sharing _API keys_. this alone cause its own host of issues:
    1. developers can leak out _API keys_ (for example in case of an ungraceful dispute with the owner organization)
    1. developers working on one **consumer** service can inadvarently affect services provided by the **provider**, partially or totally breaking functionality of some other **consumer** service.
    1. developers cannot readily distinguish the usage of their **consumer** services.
1. the _API key_ usually is the only security measure in-place. in case of a MITM attack (for example, an occasional failure of the TLS/SSL layer between **consumer** and **provider**), all forms of secrecy in the protocol is lost.
1. the process is extremely tedious and unstandardized.

additionally, in most cases that involve some financial aspect, the cost for the **consumer** would be tied in some way to the number of _API calls_ they make to the the **provider**, for calculating which they should also completely rely on the truthfulness of the **provider**. even in case of truthful providers, this will at least affect the incentives of the providers to maintain and/or improve the quality and reliability of their usage measurement mechanisms. this would also in-turn fallback on the credibility of the provider entity, increasing the entry barrier for service providers to be able to offer services feasibly in the market.

in case of the second category integration, although in the scope of these documents it is percieved as a specific case of the general problem (outlined above), as it currently stands, some frameworks are in-place for conducting such integrations, in the specific case that the **authorizer** is an end-user, and with conceptual restrictions on the functionality/data that is to be provided, namely, OAuth/OAuth2.0 and OpenID protocols. however, in this context, these have the following issues as well:

1. these frameworks do not support systematic **authorizer**s, such as a third-party service.
1. these frameworks are mainly developed as backbones of wide-spread universal authentication and authorization services, and are mainly used as such. as a result, it is not a trivial task for any developer of a **provider** service to set-up such a system, and most companies will not choose to invest the necessary time and funds at least in early stages of their operation, increasing the entry barrier for **provider** services providing such functionality/data.
1. there are ongoing discussions about security and robust-ness of some of these protocols. most nominally, there are [good arguments by some of the original authors of OAuth2.0 on the aforementioned issues](https://hueniverse.com/oauth-2-0-and-the-road-to-hell-8eec45921529), and considering OpenID also relying on the protocol for authorization, basically brings into question the long-term sustainibility and more importantly widespread adoptability of these protocols, as as it stands, relatively few providers offer such authentication and authorization mechanisms (though mainly due to the previous issue).
