---
title: Configuration
linkTitle: Configuration
weight: 5
description: >
  Overview of the Server Configuration of Aletheia?
---

### Schemas

Aletheia has the following 4 schemas present:

| Name | Description |
| --- | --- |
| core | This standard schema is released with most LDAP distributions. |
| cosine | This schema is released with a standard OpenLDAP distribution. |
| inetorgperson | The inetOrgPerson object class is a general purpose object class that holds attributes about people.  The attributes it holds were chosen to accommodate information requirements found in typical Internet and Intranet directory service deployments. Further reading at [rfc2789](https://www.rfc-editor.org/rfc/rfc2798.html) |
| rfc2307bis | Draft at [draft](https://datatracker.ietf.org/doc/html/draft-howard-rfc2307bis-02) |


### Modules
| Name | Description |
| --- | --- |
| memberof | | 
| refint | |
| ppolicy syncprov back_ldap back_monitor dynlist autogroup
| 


### Aletheia Accounts
../../../../../../Stash/aletheia/image/entities/users/01-replicator.ldif ../../../../../../Stash/aletheia/image/entities/users/02-reader.ldif ../../../../../../Stash/aletheia/image/entities/users/03-propagator.ldif ../../../../../../Stash/aletheia/image/entities/users/04-observer.ldif ../../../../../../Stash/aletheia/image/entities/users/05-aletheia.ldif

### Security
```
# Set Access
# TODO: Document Access
dn: olcDatabase={1}{{ ALETHEIA_SERVER_BACKEND }},cn=config
changetype: modify
delete: olcAccess
-
add: olcAccess
olcAccess: to * 
  by dn.exact=gidNumber=0+uidNumber=0,cn=peercred,cn=external,cn=auth manage 
  by * break
olcAccess: to attrs=userPassword,shadowLastChange 
  by self write 
  by dn="cn=admin,{{ ALETHEIA_SERVER_BASE_DN }}" write 
  by dn="cn=propagator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" write 
  by dn="cn=replicator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-write,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" write
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-admin,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" write
  by anonymous auth 
  by * none
olcAccess: to attrs=pwdFailuretime,pwdChangedTime,pwdHistory,pwdAccountLockedTime,pwdGraceUseTime
  by self none
  by dn="cn=admin,{{ ALETHEIA_SERVER_BASE_DN }}" manage 
  by dn="cn=propagator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" manage
  by dn="cn=replicator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read
  by dn="cn=aletheia,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-read,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" read
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-write,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" write
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-admin,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" manage
  by * none
olcAccess: to * 
  by self read 
  by dn="cn=admin,{{ ALETHEIA_SERVER_BASE_DN }}" write 
  by dn="cn=propagator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" write 
  by dn="cn=reader,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read 
  by dn="cn=replicator,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read 
  by dn="cn=aletheia,ou=self,{{ ALETHEIA_SERVER_BASE_DN }}" read
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-read,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" read
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-write,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" write
  by group.exact="cn={{ ALETHEIA_SERVER_ENVIRONMENT }}-aletheia-admin,{{ ALETHEIA_SERVER_ADMIN_GROUP_RDN }},{{ ALETHEIA_SERVER_BASE_DN }}" write
  by * none

```