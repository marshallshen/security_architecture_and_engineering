# software crypto

### Encryption

* CBC mode is usually a good choice
* Where does `Initalized Vector` come from?
    * Must be randomized
* Keys: it can be supplied by user.

### Disk Encryption
* `VERY IMPORTANT`, given that "delete" operations do not really delete data.

### Store Encryption Key
* Tradeoff: availability vs. confidentiality and integrity
* User store a key on disk, encrypted.
    - Decrypt it with passphrase.
* `Protecting cryptographic key` is the most important part in crypt.

### Software random number generator
* Many operating systems can provide cryptographic-grade random numbers
* `/dev/random`: True random numbers, from hardware sources
* `/dev/urandom`: Software random number generator, seeded from hardware

#### DUAL EC DBRG: The NSA Back Door
> Pseudo random number generator, read [more](http://en.wikipedia.org/wiki/Dual_EC_DRBG).

* Security company RSA made it the default in their product, allegedly after being paid off. 
* The algorithm includes a "`random`" constant
* If it’s not random—if it’s the public key in an elliptic curve cryptosystem, then you obtain the private key.

### Crypto example
```
$ cattach /usr/mab/secrets matt
Key:
$ ls -ld /crypt/matt
drwx------ 2 mab 512 Apr 1 15:56 matt
$ echo "murder" > /crypt/matt/crimes
$ ls -l /crypt/matt
total 1
-rw-rw-r-- 1 mab 7 Apr 1 15:57 crimes
$ cat /crypt/matt/crimes
murder
$ ls -l /usr/mab/secrets
total 1
-rw-rw-r-- 1 mab 15 Apr 1 15:57 8b06e85b87091124
$ cat -v /usr/mab/secrets/8b06e85b87091124
M-Z,k\x{02C6}]\x{02C6}B\x{02C6}VM-VM-6A\x{02DC}uM-LM-_M-DM-\x
```