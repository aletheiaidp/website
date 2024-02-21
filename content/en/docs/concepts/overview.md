---
title: Overview
linkTitle: Overview
weight: 1
description: >
  An overview of Aletheia and its ecosystem
---

## What is Aletheia?

This page is an overview of Aletheia. Aletheia is a set of tools for deploying and managing a directory service in a cloud native fashion. 

The name Aletheia originates from Greek mythology where Aletheia was the personified spirit of truth and sincerity. Aletheia is meant to serve as the single source of truth for identities within a system. Battle tested at [Mudrex](https://mudrex.com/), Aletheia has been providing identities and groups since 2022.

Concretely aletheia aims to **simplify the directory service ecosystem.**

## Why Aletheia?

The directory service landscape has been dominated by Microsoft's Active Directory. Open source projects such as OpenLDAP and 389 Directory Server are also present, but there is no cloud-native way to deploy and manage them. One can find a host of tutorials online focusing on installing OpenLDAP on a bare server and running it there. 

Aletheia, built on top of OpenLDAP, serves to solve these cross cutting concerns. Aletheia provides you with:

* **Cloud Native**
  All components of Aletheia have been packaged as containers. This means that you can run Aletheia on a container orchestration engine (Kubernetes, Amazon ECS) of your choice.
* **High Availability**
  Aletheia will run openldap servers in high availability in active-passive mode. This will ensure disastor recovery and make the directory service avaiable all the time.
* **Horizontal Scaling**
  Leveraging OpenLDAP's replication feature, Aletheia will provide a host of consumers to handle read load which can be horizonatally scaled.
* **Notification & Change Management**
  End users will be notified by Aletheia on password expiry dates and a nice UI will allow them to change their passwords seamlessly.
* **Simplified Administration**
  Admins will now be able to perform admin operations via a suite of command line tooling made avaiable by Aletheia.

## What's Next?

* Take a look at the [Aletheia Architecture](/docs/architecture/)
* Take a look at the [Aletheia Components](/docs/components/)
* Ready to [Get Started](/docs/setup/)?