# Analyze overall system
> You didn't build the system, but you are called to analyze if the system is secure. `Not everyone had the training you did`.

> The earlier security check is done for the system, the better.

> `Analyzing systems`: fewer components than line of code, yet many details are abstracted away.

## System Performance
* A property of the system, not any single component.
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