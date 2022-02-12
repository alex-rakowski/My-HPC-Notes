# Useful Commands


## check if any file path lengths are longer that 99 characters (+2 for ./)
```
find -regextype posix-extended -regex '.{101,}'
```
