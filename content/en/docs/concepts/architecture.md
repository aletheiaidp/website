---
title: Architecture
linkTitle: Architecture
weight: 2
description: >
  An overview of Aletheia's architecture
---

The document outlines the high level architecture of a complete Aletheia cluster. Aletheia is a set of components with distinct and decoupled purposes. The components can be categorized as follows: 

- Server
- API
- Worker

```
                     ┌−−−−−−−−−−−−−−−┐
                     ╎      api      ╎
                     ╎               ╎
                     ╎ ┌───────────┐ ╎
                     ╎ │   rest    │ ╎
                     ╎ └───────────┘ ╎
                     ╎               ╎
                     └−−−−−−−−−−−−−−−┘
                         │
                         │
                         ▼
┌−−−−−−−−−−−−−−┐     ┌−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−┐
╎    worker    ╎     ╎                      server                     ╎
╎              ╎     ╎                                                 ╎
╎ ┌──────────┐ ╎     ╎ ┌───────────┐       ┌───────┐     ┌───────────┐ ╎
╎ │ listener │ ╎ ──▶ ╎ │ consumers │ ────▶ │ proxy │ ──▶ │ providers │ ╎
╎ └──────────┘ ╎     ╎ └───────────┘       └───────┘     └───────────┘ ╎
╎              ╎     ╎                                                 ╎
└−−−−−−−−−−−−−−┘     └−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−−┘
                         ▲
                         │
                         │
                     ┌−−−−−−−−−−−−−−−┐
                     ╎    worker     ╎
                     ╎               ╎
                     ╎ ┌───────────┐ ╎
                     ╎ │ notifier  │ ╎
                     ╎ └───────────┘ ╎
                     ╎               ╎
                     └−−−−−−−−−−−−−−−┘
```

### Server
A Server is the heart of Aletheia, running an LDAP database.

Aletheia provides OpenLDAP as the database.

### API
The API provides an interface to communicate with the backing datastore apart from the LDAP protocol.

Aletheia supports a REST API.


### Workers
Workers perform asynchoronous operations on the server. Listening on change events or periodically polling to check whether the user's password is going to expire or not are all part of the worker's responsibility.

Aletheia has 2 workers - listener and notifier.

## What's Next?

* Take a look at the [Aletheia Components](/docs/components/)
* Ready to [Get Started](/docs/setup/)?