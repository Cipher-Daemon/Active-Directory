# Protected Users

To Enable Auditing 

```powershell
$ProtectedUsersLogs = @(
    'Microsoft-Windows-Authentication/AuthenticationPolicyFailures-DomainController'
    'Microsoft-Windows-Authentication/ProtectedUser-Client'
    'Microsoft-Windows-Authentication/ProtectedUserFailures-DomainController'
    'Microsoft-Windows-Authentication/ProtectedUserSuccesses-DomainController'
)

foreach ($log in $ProtectedUsersLogs){
    $EnableLog = Get-WinEvent -listlog $Log
    $EnableLog.IsEnabled = $True
    $EnableLog.SaveChanges()
}
```
