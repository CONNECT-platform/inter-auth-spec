# InterAuth specification

these documents aim to provide an interoperable, secure and easy-to-develop framework for seamless communication between various (micro)**services** in various scenarios. to be more specific, these documents focus on one **service**, **consumer**, requesting some functionality or data from another **service**, **provider**, with them most probably being developed and maintained by separate entities, and probably some financial transaction required in exchange for the services of the **provider**. these documents aim to put forth a specification such that implementations conforming to said specification can facilitate such integrations in a secure and highly interoperable manner.

targeted integrations can be broken into two categories:

1. **direct integration**: where the functionality/data provided by the **provider** merely relates to the **consumer**, or by some other measure the **provider** can and will provide the aforementioned functionality/data to the **consumer** without authorization of any third-party being required

1. **authorized integration**: where the functionality/data provided by the **provider** relates to, or by some other measure requires approval of a third-party, the **authorizer**

## contents

for easing the process of accessing and reading different sections of this specification, it is broken down into several documents.


1. ### [motivation](MOTIVATION.md)
    1. #### [background](MOTIVATION.md#background)
    1. #### [direct integration](MOTIVATION.md#direct-integration)
    1. #### [authorized integration](MOTIVATION.md#authorized-integration)
1. ### [goals](GOALS.md)
    1. #### [interoperability](GOALS.md#interoperability)
    1. #### [flexibility](GOALS.md#flexibility)
    1. #### [security](GOALS.md#security)
    1. #### [seamlessness](GOALS.md#seamlessness)
    1. #### [stateless-ness](GOALS.md#stateless-ness)
    1. #### [reusability](GOALS.md#reusability)
1. ### [terminology](TERMINOLOGY.md)
    1. #### [conformity](TERMINOLOGY.md#conformity)
        1. ##### [standard implementation](TERMINOLOGY.md#standard-implementation)
        1. ##### [requirement indicators](TERMINOLOGY.md#requirement-indicators)
    1. #### [common terms](TERMINOLOGY.md#common-terms)
        1. ##### [service](TERMINOLOGY.md#service)
        1. ##### [root address](TERMINOLOGY.md#root-address)
        1. ##### [endpoint](TERMINOLOGY.md#endpoint)
        1. ##### [signing](TERMINOLOGY.md#signing)
        1. ##### [self-signing](TERMINOLOGY.md#self-signing)
    1. #### [network](TERMINOLOGY.md#network)
        1. ##### [trusted entities](TERMINOLOGY.md#trusted-entities)
        1. ##### [providers/consumers](TERMINOLOGY.md#providersconsumers)
        1. ##### [integration](TERMINOLOGY.md#integration)
1. ### notation
1. ### [security](SECURITY.md)
    1. #### [secure communication](SECURITY.md#secure-communication)
        1. ##### [standard implementation](SECURITY.md#standard-implementation)
        1. ##### [external communication](SECURITY.md#external-communication)
    1. #### [signatures](SECURITY.md#signatures)
        1. ##### [standard implementation](SECURITY.md#standard-implementation-1)
1. ### protocols
    1. #### direct integration
    1. #### authorized integration
1. ### security analysis
1. ### further work
