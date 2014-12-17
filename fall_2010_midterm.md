# Fall 2010 Midterm

## 1
(20 points) Suppose I were concerned that substitutes were taking this exam, instead of the actual enrolled students. What form of authentication could I use? Note: the total enrollment in the class is 40. I know of no secret university resources I could use, such as fingerprint databases; anything you specify has to be contained to this class.

> The best solution is probably looking at the picture on the CUID, and perhaps comparing a signature with that on some other piece of identification such as a driver’s license or passport.

> It is worth noting that for exams with more serious security threats — e.g., the LSAT (Law School Admission Test), there are stringent authentication measures, up to and including fingerprinting.

## 2
You’re working in software development environment for a medium-sized company. There is a development copy of the code; there is also a separate copy for each release in the field, plus a patched version of each release that incorporates bug fixes.

Developers can make changes to the development copy. The manager of the development group is the only person allowed to create new releases and at some point copy the development version to a new release directory. Testers look only at release directory trees. Maintenance programmers develop patches for each release.
   
(a) (5 points) What form of access control mechanisms would you use for this setup? (Don’t bother
talking about version control systems; that’s not what any part of this question is about.)

> Access control lists, with groups used for each role. Simple user/group/other doesn’t work because some files need different group permissios for different roles.

(b) (10 points) I’ve identified four roles: developers, manager, testers, and maintainers. I’ve also identified three sets of files: development versions, release versions, and patched versions. Draw the access control matrix and show who has which permissions.

```
devel release patch
Developers rw - -
Manager r rw -
Testers - r -
Maintainers - r rw
Other permissions, such as ’x’, aren’t really relevant here|
```

## 3


