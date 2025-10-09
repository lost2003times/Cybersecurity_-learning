___
### Domain Controllers
- A domain controller is a server with thee AS DS server role installed that has specifically been promoted to a domain controller.

1. Host a copy of the AD DS directory store.
2. Provide authentication and authorization services.
3. Replicate updates to other domain controllers in the domain and forest.
4. Allow administrative access to manage user accounts and network resources.

### AD DS Data Store
- The AD DS data store contains the database files and processes that store and manage directory information for users, services and applications.

1. Consists of the Ntds.dit file.
2. Is stored by default in the %SystemRoot%/NTDS folder on all domain controllers.
3. Is accessible only through the domain controller processes and protocols.
