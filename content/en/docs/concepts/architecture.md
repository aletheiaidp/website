---
title: Architecture
linkTitle: Architecture
weight: 2
description: >
  An overview of Aletheia's architecture
---

The document outlines the high level architecture of a complete Aletheia cluster.

{{< figure src="/images/docs/architecture/overall.svg" alt="Overall Architecture" class="diagram-large d-flex justify-content-center" >}}


## Request Flow
1. A client/application connects to a load balancer.
2. The load balancer forwards this request to a bunch of consumer nodes.
3. The consumers will return read responses and will forward write requests to aletheia's proxy component.
4. The proxy forwards the write request to the active provider node. A standby node is present for automatic failover in case the active provider goes down.

## What's Next?

* Take a look at the [Aletheia Components](/docs/components/)
* Ready to [Get Started](/docs/setup/)?