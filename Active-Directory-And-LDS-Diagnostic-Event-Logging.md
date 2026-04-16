# How to configure Active Directory and LDS diagnostic event logging

More information follow [this](https://learn.microsoft.com/en-us/troubleshoot/windows-server/active-directory/configure-ad-and-lds-event-logging) link.

Domain controller: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\NTDS\Diagnostics`

LDS: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\<LDS instance name>\Diagnostics`

1. Knowledge Consistency Checker (KCC)
2. Security Events
3. ExDS Interface Events
4. MAPI Interface Events
5. Replication Events
6. Garbage Collection
7. Internal Configuration
8. Directory Access
9. Internal Processing
10. Performance Counters
11. Initialization/Termination
12. Service Control
13. Name Resolution
14. Backup
15. Field Engineering
16. LDAP Interface Events
17. Setup
18. Global Catalog
19. Inter-site Messaging
20. Group Caching
21. Linked-Value Replication
22. DS RPC Client
23. DS RPC Server
24. DS Schema
25. Transformation Engine
26. Claims-Based Access Control
27. PDC Password Update Notifications

Modify the `Diagnostics` REG_DWORD vlaue to the following in the lext section.

## Logging Levels

> [!WARNING]
> Setting diagnostic level to a 3 or higher is **NOT** recommended! Logging levels to a 3 or higher requires more resources and could impact server performance. Always set the registry value to 0 when you are done investigating.

|Level| Function|Note|
|---|---|---|
|0|None|Default value. Needs to be set back to this when investigation is completed.|
|1|Minimal|High level of events recorded.|
|2|Basic||
|3|Extensive|more detailed than lower levels.|
|4|Verbose||
|5|Internal|Logs all events.|
