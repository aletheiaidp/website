---
title: Replication
linkTitle: Replication
weight: 4
description: >
  How is Aletheia replicating data?
---

### Replication

Aletheia uses the **Syncrepl** Protocol of LDAP with the **RefreshAndPersist** operation for replication between the provides and between the provider and consumer nodes. 

The consumer polls the provider using an LDAP Serach Request with an LDAP Sync Control attached. This synchronization search remains persistent in the provider. Subsequent updates to the synchronization content in the provider cause additional entry updates to be sent to the consumer.

The provider nodes replicate from each other using **MirrorMode**. MirrorMode provides all of the consistency guarantees of single-provider replication, while also providing the high availability of multi-provider. Aletheia Proxy is employed as an external frontend is employed to direct all writes to only one of the two servers. When one provider goes down, the proxy will switch to directing all writes to the second provider. When the crashed provider is repaired, it will automatically catch up to any changes made and resync.

### Chaining

In order to separate provider nodes (read/write nodes) from consumer nodes (read nodes), Aletheia uses the chaining overlay. Any write request which comes to the consumer is redirected to the provider and then subsequently synced back to the consumer.

