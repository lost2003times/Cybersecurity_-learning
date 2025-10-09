___
### AD DS Schema
- Defines every type of object that can be stored in the directory.
- Enforces rules regarding object creation and configuration.


| Object Types     | Funtions                                       | Examples        |
| ---------------- | ---------------------------------------------- | --------------- |
| Class Object     | What objects can be created in the directory.  | -User, Computer |
| Attribute Object | Information that can be attached to an object. | -Display name   |

### Domains
- Domains are used to group and manage objects in an organization.

1. An administrative boundary for applying policies to groups of objects.
2. A replication boundary for replication data between domain controllers.
3. An authentication and authorization boundary that provides a way to limit the scope of access to resources.

### Trees
- A domain tree is a hierarchy of domains in AD DS

1. Share a contiguous namespace with the parent domain.
2. Can have additional child domains.
3. By default create a two-way transitive trust with other domains.

### Forests 
- A forest is a collection of one or more domain trees.

1. Share a common schema
2. Share a common configuration partition.
3. Share a common global catalog to enable searching.
4. Enable trust between all domains in the forest.
5. Share the Enterprise Admins and Schema Admins groups.

### Organizational Units (OUs)
- OUs are Active Directory containers that can contain users, groups, computers and other OUs.

1. Represent your organization hierarchically and logically.
2. Manage a collection of object in a consistent way.
3. Delegate permissions to administer groups of objects.
4. Apply policies.


### Trusts
- Trusts provide a mechanism for users to gain access to resources in another domain.

![](Courses/TCM%20Practical%20Ethical%20Hacking/Domain%206%20-%20Active%20Directory/assests/Pasted%20image%2020251009222024.png)

1. All domains in a forest trust all other domains in the forest.
2. Trusts can extent outside the forest.


### Objects


| Object        |     |
| ------------- | --- |
| User          |     |
| InetOrgPerson |     |
| Cont          |     |
