# Analyze overall system
> You didn't build the system, but you are called to analyze if the system is secure. `Not everyone had the training you did`.

> The earlier security check is done for the system, the better.

> `Analyzing systems`: fewer components than line of code (`easier`), yet many details are abstracted away (`harder`).

## System Performance
* A property of the system, not any single component.
    * How many elements depends on what level you are looking at (think of looking down from a flight.. What you see depends on how high you are in the sky).
* Finding bottlenecks is important, however programmers' guess are `often wrong`.
* Major performance improvements generally come from algorithmic changes, not from minor tweaks.
* Build first, then measure, then optimize — but don’t surrender correctness.

## System Elements
* Web servers, database engines, etc.
* Each element itself is a complex system.
* Clarify each I/O: 
    * where its inputs come from
    * what its outputs
    * what happen if something is corrupted
* When accessing elements
    * What are the forms of access (token, password, RSA keys)?
    * What sorts of access controls are there?
    * Has the access being logged anywhere?
* How does data flow across elements?
    * Who talks to whom?
    * What's the protocol?
    * Is protocol safe?

### Input filtering
* Where can enemy input enter the system?
* Are inputs properly checked?
* What about back channels, such as DNS?
    * Shellshock was used inside DNS to attack Apple servers.

## System Management
* More connectivities are needed to access different components of system.
* System backups:
    * How are disks backed up? Are backup settings different across different servers?

> Where experience matter: what parts of the design seem more vulnerable?
    * What parts of the design seem problematic?
    * Some pieces are weaker than others?
    * Trust your feeling, Luke.

