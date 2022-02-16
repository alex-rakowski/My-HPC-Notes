# Useful Commands


## check if any file path lengths are longer that 99 characters (+2 for ./)
```
find -regextype posix-extended -regex '.{101,}'
```
## recursively change file text in file
```
grep -rl "1.000000 1.000000" . | xargs sed -i 's/1.000000 1.000000/1.000000 0.078000/g'
```
