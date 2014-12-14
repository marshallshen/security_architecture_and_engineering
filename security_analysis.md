# Security Analysis

## Attacking Things
> It takes a thief to catch a thief

## Construction vs. Destruction
* An architect and a demonlition expert need to know about.
* Architect balance costs, 
* Demolition engineer works with what he got, what he needs is very different.

> Some design decisions are very hard to correct later on.
> Have frequent reviews.

> Early reviews: broad architecture

> Later reviews: implementation details


## What to analyze?
* Individual programs
* Overall system flow

## `date` command
```
$ date
Mon Nov
$ TZ=/usr/shar/zoneinfo/Pacific/Guam date
Tue Nov ... ChST 2008
```

## Testing
> Bling tests, however may `not` save us because system requirements can change.

> Look for potentially dangerous calls: `fgets`, `strcpy`..

> Use `grep` to find danagerous spots

### Flow path analysis
> Subprocedures make life difficult

> Understand `flow path of the program` $$\rightarrow$$ compliers do that!

```
$ cflow env/*.c
```
Note that cflow also has graphical call flow.

### Data Flow Analysis
>  Assign initial input, mutate inputs, run programs.

> Complexity is the enemy of security

> System performance is usually a property of the system, not any single component

> Most code is not `performance-sensitive`: it's either not executed at all or executed rarely.

### Analysis tools


### Digression: Run-Time checks
> TODO: Perl's `tainted mode`.

> chr buf[1024] (potentially dangerous) or `malloc`(more dynamic..) is called

### System analysis (web servers, database engines, etc.)

> Whare are the elements of a system (different angle) $$\rightarrow$$ high level architecture view.

> `What are the data flows among different elements`?
    * What is input / output? Is input encrypted?
    * Where can enemy input enter the entire system?

> Analyzing system elements: `access control`; `logging`..

> How high is `the security barrier`? How strong is the firewall.

> How are disks `backed up`? How are the `back-up` being protected?



