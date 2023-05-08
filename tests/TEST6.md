# TEST 6

## Testing

```
# Should show envvars
set

# Should echo some stuff
# NOTE: Important note for the markdown file that doesnt need to be in the test description
echo "some stuff"

# Should concatenate three commands together
set TEST=thing
set | findstr TEST | findstr thing
set TEST=
```

