# Buffer overflow

### Bad code example (4.3BDS `fingerd` command)
```
char line[512];
...
gets(line);
```
### Java vs. C.
* Java, C#, Go check array bounds
* More or less everything but C and C++ check

![buffer_overflow_1]()
![buffer_overflow_2]()
![buffer_overflow_3]()
![buffer_overflow_4]()