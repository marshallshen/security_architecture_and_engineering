# Fall 2014 Midterm

1. (15 points) Someone has built a JPG virus embedded in pictures (of kittens?). The picture triggers
a bug in common image display software, thereby infecting the machine. The virus can only infect
other JPGs—but JPGs can arrive via email (including encrypted email), social networks, other web
sites, flash drives, and more. Both desktops and phones are susceptible to the virus. The virus is
highly polymorphic and encrypted; it sometimes changes more rapidly than the virus definitions can be
updated.
What is the best strategy for an organization to stop this malware?

2. (15 points) To aid in generating random cryptographic keys, every employee of a company has a mag stripe card and a keyboard with a mag stripe reader. To generate a new key, the employee swipes the card; a secret value from the card is cryptographically combined with the time of day. (Assume that the combination algorithm is cryptographically correct.) Outline some possible attacks against this system. If you need to make any assumptions, state them explicitly—and make sure that they’re plausible.

3. (20 points) Consider the design of a distributed computer system where the components are connected by an ordinary network and the user workstations have no privileged operations. Effectively, each user is root or Administrator on his or her machine. Instead, there are a few privileged computers that implement the file system, etc. Give at least two of the security challenges of this design? How would
you solve these problems?

4. You’re designing the authentication system for a multi-level secure system. The system will hold data at all levels from `Unclassified` to `Top Secret`. (For convenience, I’ve included the lattice diagram
from class.)

(a) (10 points) One proposal is to use passwords; that, though, requires a password file. One group suggests labeling the password file as <High, PW>; another group suggests hLow, PWi. Give one advantage of each possibility

