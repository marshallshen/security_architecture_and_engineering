# Secure C practice

### Array-bound checking
> The first principle was security: . . . A consequence of this principle is that every occurrence of every subscript of every subscripted variable was on every occasion checked at run time against both the upper and the lower declared bounds of the array... I note with fear and horror that even in 1980, language designers and users have not learned this lesson. In any respectable branch of engineering, failure to observe such elementary precautions would have long been against the law.

> Hoare’s Turing Award Lecture, 1980

* Challenge: `array vs. pointer` semantics makes it harder in C.
* A bounds-checking C compiler has been written, but it’s largely unused.

### Format strings
* `printf(str)` is bad $$\rightarrow$$ metacharacters can confuse log files.
* `printf("%s", str)` is good
* `%n` is the worst
    - `printf("Hello\n%n", &cnt)` can be used to overwrite memory location!

### System requirement
> Make error-case specific!

> “File names may be up to 1024 bytes long” `vs`

> “File names may be up to 1024 bytes long; longer file names must be rejected”

* Second form alerts the programmer to the real requirement
* Second form alerts the tester to the requirement
* Testing is done against requirements!

### Input validation
> A program whose behavior has not been specified cannot be buggy, only surprising.

* Trust nothing supplied by the use
* Define inputs before they can be checked
    - "Is a newline a valid character in a username?"





