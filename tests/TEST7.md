# TEST 7

## Testing

```powershell
# Should show envvars
Get-ChildItem Env:

# Should echo some stuff
# NOTE: Important note for the markdown file that doesnt need to be in the test description
Write-Output "some stuff"

# Should concatenate three commands together
Write-Output "some stuff"
Write-Output "yup" | Select-String -Pattern "yup"
Get-ChildItem Env:
```

