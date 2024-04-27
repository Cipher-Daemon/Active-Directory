# Generating Users

Run the following script below to use the Random Names list to generate users (note this will take time so be patient.)

```powershell
$LastNames = Get-Content -Path .\Random-Lastnames.txt
$FirstNames = Get-Content -Path .\Random-Firstnames.txt
$combinations = @()
$FCount = $FirstNames.count
$LCount = $LastNames.count
$FInt = 1
$LInt = 1
$Tint = 1
foreach ($firstName in $firstNames) {
$FPercent = ($Fint/$FCount) * 100
$FRoundPercent = [math]::Round($FPercent,2)
write-progress -Activity "First Names ($Fint out of $FCount)" -status "$FRoundPercent Percent Complete" -percentcomplete $FPercent
    foreach ($lastName in $lastNames) {
	$LPercent = ($Lint/$LCount) * 100
    $LRoundPercent = [math]::Round($LPercent,2)
	write-progress -Activity "Last Names ($Lint out of $LCount)  -- $TintComma Names Created so far in total." -status "$LRoundPercent Percent Complete" -percentcomplete $LPercent -id 1
       
        $combinations += [PSCustomObject]@{
            FirstName = $firstName
            LastName = $lastName
        }
	$LInt++
    $Tint++
    $TIntComma = '{0:N0}' -f $Tint
    }
$combinations | Export-Csv -Path "combinations.csv" -NoTypeInformation
$Fint++
$Lint = 1
$combinations = @()
}
```
