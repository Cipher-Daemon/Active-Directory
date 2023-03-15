# Test SRV Record Lookup

Want to verify if DNS is working for your domain or if the workstation is having issues connecting?

Try the following to test this:

1. Open a command prompt or a powershell window and start NSLOOKUP.
```cmd
nslookup
```
2. Make sure that setting the record is set to all.
```
set type=all
```
3. type in the SRV record for LDAP, 
```
_ldap._tcp.<internal domain>
```

## Example
If your internal domain is Lab.local the ldap lookup record would be this:
```
_ldap._tcp.lab.local
```
