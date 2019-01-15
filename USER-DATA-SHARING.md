# User Data Sharing InterAuth Spec

This document aims to specify methods in which two (micro)services would integrate with each other, in a scenario where
one service is a **data host**, or **host** for short, as it maintains access to some specific and shareable user-data, and
the other is an **requester**, as it requests access to the information or requests
permission to conduct specific operations on the data through the **data host** as a **provider**, and the permission
should be given by the user who the information is attributed to, i.e. the **owner**.
