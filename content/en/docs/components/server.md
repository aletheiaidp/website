---
title: Server
weight: 20
description: >
  An overview of Aletheia's server component
---


1. A client/application connects to a load balancer.
2. The load balancer forwards this request to a bunch of consumer nodes.
3. The consumers will return read responses and will forward write requests to aletheia's proxy component.
4. The proxy forwards the write request to the active provider node. A standby node is present for automatic failover in case the active provider goes down.

Consumers are read nodes of OpenLDAP which replicate from a provider. Consumers need ephemeral storage since they always replicate from the provider to be fully consistent. They are horizontally scalable.


An Aletheia provider is a read-write node of OpenLDAP. It is responsible for storing the state of the directory. All write operations take place at this node.