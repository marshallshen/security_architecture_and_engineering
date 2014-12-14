# Analyze individual programs

## What to look for?
* Typical errors: buffer overflow, race conditions, etc.
    * Buffer overflow candidates: `gets()`, `strcpy()`, `sprintf()`..
    * TOCTTOU races: `access()`, `stat()` other than `fstat()`..
    * Not as easy as it sounds -- buffer sizes not always obvious

    ```c
    void buildmsg(char *dst, char *s, char *msg){
    sprintf(dst, "Error: %s: %s\n", s, msg);
    return;
    }
    ```
* Only check `security sensitive` programs.
    * Case Study: `date` command
    ```
    $ date
    Mon Nov 17 21:51:03 EST 2008
    $ TZ=/usr/share/zoneinfo/Pacific/Guam date
    Tue Nov 18 12:51:11 ChST 2008
    $ TZ=/usr/share/zoneinfo/Pacific/Tahiti date
    Mon Nov 17 16:51:20 TAHT 2008
    ```
* `BLIND TESTING`: in the case of timezone, it won't find the error.
* You can write test cases $$\iff$$ there's something to test for.
    * `grep` for suspect functions.

## Why are individual programs hard to analyze?
* Subprocedures make life hard.
* Most routines are called from many different places, with different arguments.
* Arguments passed may be arguments from a higher-level procedure.
* Buffers may be dynamically allocated.





