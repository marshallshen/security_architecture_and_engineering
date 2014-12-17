# Protecting Clients

### Normally, you own your device...
* What if the enemy owns it?
* What if your enemy is supposed to own it?

## Attack
* Software
    * Use program to obtain authentication
* Physical
    * Manipulate physical environments: temperature, radio-active waves, etc.
* There are companies that professionally crack computer chips for buinsess (chipworks.com).

### Smart Cards
*  Often in credit card form factor
*  Contains small CPU and non-volatile storage (some contain an RSA accelerator chip)
* In stored value systems, the attacker wants to add more money to the card
* Alternatively, the attacker wants to extract the secret, to permit counterfeiting of more cards
* If an authentication token is locked by a PIN, the attacker wants to discover or replace the PIN

## Metro card
* MTA Metrocard: central database controlled
* Washington D.C farecard: the card itself knows its value. No protection against theft or counterfeiting.

## iPhone
- All content is encrypted with one of a set of randomly-generated AES keys
- These keys are themselves protected: either encrypted with a key derived from a random UID that is stored in a secure, on-chip area, or encrypted with a key derived from the UID and the PIN
- Hardware-enforced maximum guess rate of 80 ms/try

## Conclusion
- Many situations require that some crucial device be in enemy hands
- True security in such cases is almost impossible
- More than in most situations, this shows the role of economics: the attack has to be cost-effective
- This is usually the best approach: make the security good enough




