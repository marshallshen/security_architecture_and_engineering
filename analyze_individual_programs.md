# Analyze individual programs

## What to look for?
* Typical errors: buffer overflow, race conditions, etc.
    * Buffer overflow candidates: `gets()`, `strcpy()`, `sprintf()`..
    * TOCTTOU races: `access()`, `stat()` other than `fstat()`..
    * Check declaration, should use `malloc`:

    ```
    char buf[1024]; // bad declaration
    ```
    * Not as easy as it sounds -- buffer sizes not always obvious

    ```
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

## Flow Analysis
* We need to understand the paths to each suspect call.
* We can use compilers to help us understand complex paths (analyze call stacks, to the low level).
* Call graph:
    ```
    $ cflow env/*.c
    
    main() <int main (int argc,char **argv) at env/env.c:55>:

    setlocale()
    getopt()
    usage() <void usage (void) at env/env.c:94>:
    fprintf()
    exit()
    strchr()
    setenv()
    execvp()
    err()
    printf()
    exit()
    ```
![flow analysis]()

## Digression: Run-Time Checks
* Best example: Perl's "taint mode"
    * Data from untrustworthy sources: command-line arguments, environment variables, file input, etc. -- is marked as "tainted".
    * Any variable derived from a tainted variable is marked “tainted”.
    * Certain operations cannot be performed with tainted input; a run-time exception is generated.
    * Read [more](http://gunther.web66.com/FAQS/taintmode.html) on Perl's taint mode.

## Individual programs are hard to analyze
* Subprocedures make life hard.
* Most routines are called from many different places, with different arguments.
* Arguments passed may be arguments from a higher-level procedure.
* Buffers may be dynamically allocated.



