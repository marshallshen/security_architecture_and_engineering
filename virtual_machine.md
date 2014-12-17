# Virtual Machine (VM)

* Give the application an entire isolated “machine”, down to the (virtual) bare silicon
* Run an entire operating system on this
* Run the untrusted application on that OS
* It can be very safe

## How VMs work
* Recall the hardware access control mechanisms: privileged
operations and memory protection
* Run the guest operating system unprivileged
* Any time the guest OS issues a privileged operation, it traps to the virtual machine monitor (VMM)
* The VMM emulates the operation. For example, an attempt at disk I/O is mapped to I/O to a real file that represents the virtual disk

## VM Security
* Very strong isolation
* Very high overhead. . .
    * Must set up and administer an entire OS
    * Guest copies of Microsoft Windows require just as many patches as do native copies
*  Performance can be bad, though some hardware architectures have special instructions to improve VM performance.

## Interacting with a VM
* Often don’t want perfect isolation.
* Example: cut-and-paste between windows
* Performance can be dramatically enhanced if the guest OS signals the VMM
* Example: add a virtual “graphics” driver that calls the VMM, via the equivalent of a system call


