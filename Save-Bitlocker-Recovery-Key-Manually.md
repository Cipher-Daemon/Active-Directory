# DRAFT
  
  Run in Powershell (as domain admin)
    manage-bde -protectors -get c:
  
  
  get the Numerical password ID
  
  
  
  run this in powershell (as domain admin)
  
  manage-bde -protectors -adbackup c: -id '{FULL-ID-STRING}'
  
NOTE: it is important that you quote the ID string


## Powershell way
```
$ID = (manage-bde -protectors -get c:|select-string "id")[-1]
$NewID = (echo "$ID")
$Length = $NewID.length
$output = $NewID.Substring($Length -38)
$output

echo "manage-bde -protectors -adbackup c: -id $output"
```
