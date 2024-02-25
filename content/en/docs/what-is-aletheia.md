---
title: What is Aletheia?
linkTitle: What is Aletheia?
weight: -1
description: >
  An overview of Aletheia and its ecosystem
---

{{% pageinfo color="primary" %}}
The name Aletheia originates from Greek mythology where Aletheia was the personified spirit of **truth**.
{{% /pageinfo %}}

## What is Aletheia?
Aletheia provides a comprehensive solution that utilizes OpenLDAP for cloud-native deployment and management of directory services. While Microsoft's Active Directory has dominated the directory service landscape, there are also open-source projects like OpenLDAP and 389 Directory Server. However, these lack a cloud-native approach for deployment and management. 

The main aim of Aletheia is tobring directory services onto the cloud and to establish a single source of truth for all identities such as user accounts, access control groups, and password policies.

## Features
Aletheia, built on top of OpenLDAP, serves to solve these cross-cutting concerns. Aletheia provides a comprehensive set of features and benefits: 

- Cloud Native: All components of Aletheia have been packaged as containers. This means that you can run Aletheia on a container orchestration engine of your choice.
- High Availability:  Aletehia ensures high availability by running OpenLDAP servers in an active-passive mode for disaster recovery and continuous directory service availability
- Horizontal Scaling: Leveraging OpenLDAP's replication feature, Aletheia allows horizontal scaling with multiple consumers handling read load efficiently
- Notification & Change Management: End users will be notified about password expiry dates through notifications provided by Alteheis. An intuitive UI enables them to change their passwords seamlessly.
- Extensible API: Aletheia provides a REST-based API for interacting with the directory information tree.

## Components
The Aletheia system offers a range of components, each serving a specific and distinct purpose:
- [server](/docs/components/server/) runs the database server.
- [api](/docs/components/api/) provides REST endpoints for managing or interacting with the OpenLDAP database.
- [worker](/docs/components/worker/) is responsible for monitoring the OpenLDAP database and sending notifications/alerts.
- [proxy](/docs/components/proxy+), manages a HAproxy server to enable automatic failover between active and standby server nodes.

## What's Next?

* Take a look at the [Aletheia Architecture](/docs/architecture/)
* Take a look at the [Aletheia Components](/docs/components/)
* Ready to [Get Started](/docs/setup/)?