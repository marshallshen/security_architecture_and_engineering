# Case study: Web Browser
## Challenges:
* Structural separation of programs
* Backwards compatibility
    * E.g Windows Vista and IE 6
    > Windows started to use `sandboxing`, so browser has less priviledges.

## Components of web browser security
1. User Account Control (UAC)
2. Mandatory Integrity Control (MIC)
3. User Interface Priviledge Isolation (UIPI)

### User Account Control
- Eliminate need to log in as Adminstrator
- If you want to perform priviledged action, you need to provide adminstrator's key.

### Mandatory Integrity Control
> Security design by Microsoft
- Process had different levels of priviledges
- Low-priviledge process can not write to protected files
- Priviledge is inherited
- "no write down"

### Virtualization
> Historically many Microsoft code is old, and designed without much thoughts in security.

> Many existing Microsoft code wants to write files: cache, temp files, cookies, history, registry, etc.

> Rather than `rewrite whole codebase`, Microsoft added a layer that `virtualizes` these function: when you try to write a file with low priviledge, you are writing to a copy of the file, save somewhere, then swap file can replace old file. `Pay down tech debt`.

> Software update (security update) vs. User convenience: `don't annoy users`!

### User Interface Priviledge Isolation
> Access control for message passing: prevent `low-priviledge process` to send message to `high-priviledged process`.

> Microsoft: separate Ineternet Explorer from Windows Explorer(i.e. restored the distinction between net and desktop)

### Securing web browser
> Firefox runs as one process
> Chrome and IE 8 use a process per tab.




