---
title: Components
weight: 20
description: >
  An overview of Aletheia's components
---

The document outlines all the components you need to run a working Aletheia cluster.

## Components
Aletheia has been built on the cobra command line cli. The following commands (each translating to one or components) are available: -

* `server`([docs](/docs/components/server/)), runs the OpenLDAP server in various modes. Currently, `provider` and `consumer` modes are avaiable.
* `api` ([docs](/docs/components/api/)), exposes REST endpoints for administrating or simply interacting with the OpenLDAP database. It is particularly useful for facilitating password operations such as checking and changing passwords.
* `worker` ([docs](/docs/components/worker/)), is responsible for polling the OpenLDAP database and sending notifications to accounts for password expiry.
* `proxy` ([docs](/docs/components/proxy/)), is responsible for providing auto failover between the active and standby provider nodes.
* `manage` ([docs](/docs/components/manager/)), manages a variety of admin operations via any CLI tool.

## What's Next?
Read about the various components of Aletheia in depth