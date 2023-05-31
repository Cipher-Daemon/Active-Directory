# Group Policy Preference

## HotKeys

### System Defined Variables

You can often use variables within GPP to set values for certain things. To view the list open any GPP setting and press the **"F3"** button.

This can be useful if you are messing with multi-domain/forest scenarios where you either dont accidentally mistpye or typo a domain, computer, OS name etc.

example would be 
```
%DomainName%\Domain Admins
```

## Gotchas

Whenever you enter multiple settings that contain variables, make sure that you ALWAYS put in ALL the values that contain system variables first before the generic ones (ie. BUITIN) otherwise it'll not work as expected and there will be no errors as to why it wont work.

Example of how you would setup the GPP for Local Users and Groups Computer setting:
![image](https://github.com/Cipher-Daemon/Active-Directory/assets/105097480/a4a60d6c-7ea1-45aa-8d42-a275128bbded)
