# inter-auth-spec

these documents aim to provide a framework for seamless and secure communication between various (micro)services in various scenarios. to be more specific, these documents focus on one service, **consumer**, requesting some functionality or data from another service, **provider**, with them most probably being developed and maintained by separate entities, and probably some financial mechanism required to provide services of the **provider**. this scenario can be broken into two categories:

1. _Category 1 Integration_: where the functionality/data provided by the **provider** merely relates to the **consumer**, or by some other measure the **provider** can and will provide the aforementioned functionality/data to the **provider** without authorization of any third-party being required

1. _Category 2 Integration_: where the functionality/data provided by the **provider** relates to, or by some other measure requires approval of a third-party, the **authorizer**
