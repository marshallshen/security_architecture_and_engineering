# Email security

### Encrypt private key with user-typed passphrase
> Sometimes we can crypto with hardware assistance

## Where are the decryption and sigining done?
> When is encryption done?

> When is decryption done?
    - Think about environment
    - Decryption should `NOT` know the identity of sender, don't want to expose user signature.
    - Neither encryption nor decryption should happen at the Geataway.
> Should emails content be stored as `encrypted`?
    - Some content (eg. corporate emails), are public content

## Signing message
> Do I need to sign `every` message?
> How to balance between `signing every` and `signing none` message.

## Caching keys
> Cache keys are exposed in the mailer, can be exposed via bugs.

## Size of mailer program
> Mailer programs are BIG.

> Security hole rates go up as the square of the code size.

> Thunderbird - 6000 KLOC

> Evolution - 2500 KLOC

### Why are mailers so big?
#### Mail formats are complex:
- MIME
- Multigingual
- GUIs

#### Mailer features are complex:
- HTML rendering
- Calendar embedding
- Inline editor

#### How to separate keys from mailer application?
> Outboard Key Manager (Keyring, keyring manager)

> Make manager simple and entrusted with few responsibility

> GNOME Keyring 150 KLOC

> GNOME Keyring manager 97 KLOC

> GPG 717 KLOC

### Managing the key Manager
> The mailer still tells the key manager what to decrypt or sign.
> Hard to predict what's really being signed or decrypted.
> Tradeoff: balance between `security` and `convenience`
    - Enhance security by adding more process
    - More process means more inconvenience





TODO: DKIM (Anti-spam mechanism)
