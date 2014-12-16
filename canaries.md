## Canaries
> Buffer overflow protection

* Insert a random “canary” value between the return address and the rest of the stack frame.
* Check if it’s intact before returning. Abort if changed.
* Any stack-smash attack will have to overwrite the canary to get to the return address.
* Use a different random value each time the program is executed

![canaries](images/canaries.png)