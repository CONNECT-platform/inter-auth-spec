# InterAuth spec

these documents aim to provide a framework for seamless and secure communication between various (micro)services in various scenarios. to be more specific, these documents focus on one service, **consumer**, requesting some functionality or data from another service, **provider**, with them most probably being developed and maintained by separate entities, and probably some financial mechanism required to provide services of the **provider**. this scenario can be broken into two categories:

1. _Direct Integration_: where the functionality/data provided by the **provider** merely relates to the **consumer**, or by some other measure the **provider** can and will provide the aforementioned functionality/data to the **provider** without authorization of any third-party being required

1. _Authorized Integration_: where the functionality/data provided by the **provider** relates to, or by some other measure requires approval of a third-party, the **authorizer**

## contents

for easing the process of accessing and reading different sections of this specification, it is broken down into several documents. in the following section all these subdocuments are named in the form of a table of contents and 

1. ### preface
    1. #### [motivation](MOTIVATION.md)
    1. #### goals
    1. #### terminology
    1. #### notation
1. ### protocols
    1. #### direct integration
    1. #### authorized integration
1. ### security analysis
1. ### further work

## remarks

