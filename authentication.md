# Authentication

## Forms of Authentication

* Something you know: passwords
* Something you have: smart card
* Something you are: fingerprint

### Salt

* Pick a random number—12 bits, for Unix—and use it to modify the password-hashing algorithm
* Store the salt (unprotected) with the hashed password
* Prevent the same password from hashing to the same value on different machines or for different users
* Makes dictionary of precomputed hashed passwords much more
expensive
* Doesn’t make the attack on a single password harder; makes attacks
trying to find some password 4096× harder

### Two Factor authentication

> Two-factor authentication provides unambiguous identification of users by means of the combination of two different components. These components may be something that the user knows, something that the user possesses or something that is inseparable from the user.