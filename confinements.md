# Confinements

> Why Confinements (Separated Components)
* Isolation components to ensure security. 
* If the machine is compromised, the privileged will be set up `against` you.
* Limit each application to `a small subset` of the system's `resources`.

> Resources to protect
* CPU time
* Real and Virtual memory
* Disk space
* Network Identity
* Network Access rights...

## Limits of isolation
- Trade-off: isolation means more security and more complexity.
- "No read up, no write down": communicate IO down using something other than "write". Example: create and delete files in a shared directory.
- Covert channels:
    1. Prevent leakage of information between a high-security process and a low-security process.

- Storage channels:
    1. Modulate some share resources: e.g create and delete files in a shared directory

- Timing channels:
  1. modulate system timing in detectable way.
  2. receiver times I/O operations.

- Password-checking channel:
  1. Old OS checks password byte by byte.
  2. It returned a failure indication as soon as a byte didn't match -> the time difference leaks information on which byte of password is guessed correct to $$A$$.

- Limit covert channels:
  1. bandwith-limit, cap the rate at which certain operations can be done.
  2. add noise (randomization?)



