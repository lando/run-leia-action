# TEST 5

## Testing

```bash
# Should return true
true

# Should echo some stuff
# NOTE: Important note for the markdown file that doesnt need to be in the test description
echo "some stuff"

# Should return status code 1
cat filedoesnotexist || echo $? | grep 1

# Should concatenate three commands together
export TEST=thing
env | grep TEST
unset TEST

# Should not concatenate if escape is used
export TEST=thing \
  TEST2=stuff \
  TEST3=morestuff
env | grep TEST
env | grep TEST2
env | grep TEST3
unset TEST
unset TEST2
unset TEST3
```

