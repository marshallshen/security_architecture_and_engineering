# Virus
> Spread across `programs`

* An “Infected” program (or floppy)
* When executed, it copies itself to other places of a system.
    > `Question`: how to write a program that writes itself?
*  It may carry an extra “payload” that performs other functions

### Boot sector virus
* Modify boot sector of hard drive
* We don't boot drive that much nowadays, so boot-sector virus is largely extinct.

### Infected Flash Drive
* `autorun.inf` in flash drive is honored by many OS systems.

### Macro Virus
* Viruses can be written in any sufficiently-powerful language
* Word documents (also Powerpoint presentations and Excel
spreadsheets) can thus spread viruses, `using Microsoft Macro language`.
* Word Macro viruses spread in ordinary business!

#### E.g Latex Virus
Almost works - but the program can't open file in other directories..
```
\documentclass{article}
\begin{document}
Foo
\immediate\openout 3 infectedfile.exe
\immediate\write 3{infection}
bar
\end{document}
```

### Virus-Spreading Patterns
* Boot-sector viruses spread in affinity groups -- floppies were a normal means of communication before networks.
* Program viruses spread by people sharing software, `often improper or illegal`.

### First Virus
* A boot-sector virus written by a 15-year-old.

### Zero Virus
> A zero-day virus (also known as zero-day malware or next-generation malware) is a previously unknown computer virus or other malware for which specific antivirus software signatures are not yet available.

