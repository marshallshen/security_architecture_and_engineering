# Buffer overflow

### Bad code example (4.3BDS `fingerd` command)
```
char line[512];
...
gets(line);
```

![buffer_overflow_1]()
![buffer_overflow_2]()
![buffer_overflow_3]()