# Crypto Engineering

## Challenges
* What data to encrypt?
* Where to store keys?
* Trade-off between `confidentiality` and `availability`

## Why encrypt files:
> AGAINST THE THEVIES!

![theft]()

* File system or disk encryption `is useful` if the threat is compromise from outside the boundaries of the machine: physical theft, remote file system, backup media, etc.
* It is not useful for intra-machine threats; an enemy who can bypass access controls can steal the key or the plaintext.

### What can encryption `not` do? 
> File type is not well-protected

* Size distribution of different file types are `predictable`.

> Files of 5 MB or 6 MB are — on my disk — very likely to be NEFs; files under 5 MB or over 7 MB are never NEFs. Files of 1–3 MB are probably JPG; files 7 MB and larger are almost never JPG.


