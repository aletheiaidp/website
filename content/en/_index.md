---
title: Aletheia
---

{{< blocks/cover image_anchor="top" height="min" color="primary" >}}
<img src="/static/images/logo/light.svg" class="site-logo" />
<h2 class="mt-4">
  A distributed, reliable key-value store for the most critical data of a distributed system
</h2>
<div class="mt-5 mx-auto">
	<a class="btn btn-lg btn-secondary mr-3 mb-4" href="/docs">
		Learn more
	</a>
	<a class="btn btn-lg btn-primary mr-3 mb-4" href="/docs">
		Quickstart<i class="fas fa-arrow-alt-circle-right ml-2"></i>
	</a>
</div>
{{< /blocks/cover >}}

{{% blocks/lead color="primary" %}}
Aletheia, is an open-source system for running and managing a highly available directory server, built on [openldap](https://openldap.org/).

It provides a set of components to run a enterprise grade directory server. 
{{% /blocks/lead %}}


{{< blocks/section type="container" >}}

{{% blocks/feature %}}
#### High Availability

Highly available openldap server with 2 provider nodes in active-standby and multiple consumer nodes. An HAproxy load balancer to provider active-standby failover.

{{% /blocks/feature %}}

{{% blocks/feature %}}
#### Suite of Tools

An API to check and change passwords, A cron job to remind end users to change their passwords via AWS SES, A command to create bulk users via a CSV file

{{% /blocks/feature %}}

{{% blocks/feature %}}
#### Password Manager UI

A minimal UI for end users to change passwords

{{% /blocks/feature %}}

{{< /blocks/section >}}