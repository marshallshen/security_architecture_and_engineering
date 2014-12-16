# Crypto Engineering

## Challenges
* What data to encrypt?
* Where to store keys?
* Trade-off between `confidentiality` and `availability`

## Why encrypt files:
> AGAINST THE THEVIES!

![theft]()

### What can encryption `not` do? 
> File type is not well-protected

* Size distribution of different file types are `predictable`.

> Files of 5 MB or 6 MB are — on my disk — very likely to be NEFs; files under 5 MB or over 7 MB are never NEFs. Files of 1–3 MB are probably JPG; files 7 MB and larger are almost never JPG.

### Encryption

* CBC mode is usually a good choice
* Where does `Initalized Vector` come from?
    * Must be randomized
* Keys: it can be supplied by user.

