# software crypto

### Encryption

* CBC mode is usually a good choice
* Where does `Initalized Vector` come from?
    * Must be randomized
* Keys: it can be supplied by user.

### Disk Encryption
* `VERY IMPORTANT`, given that "delete" operations do not really delete data.

### Store Encryption Key
* User store a key on disk, encrypted.
    - Decrypt it with passphrase.