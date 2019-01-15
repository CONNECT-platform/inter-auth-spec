# Provider/Consumer InterAuth Spec

This document aims to specify ways in which two (micro)services, possibly developed and maintained by two different entities
(teams, companies, etc) would seamlessly integrate into each other, in a scenario that one service is a **provider**, as in 
it provides a specific service, and the other is a **consumer**, as in they utilize the services provided by the **provider**
to incorporate them to offer services to some other service or component, may it be a consumer-facing interface or other
services.
