# OS Booting Specifications

This document will outline how the OS startup process works.

## Boot procedure

* Stage 0 (firmware): UEFI firmware loads `BOOTMAN.EFI` from ESP on a root disk
* Stage 1 (boot manager): `BOOTMAN` loads `OSKernel.efi` from Disk. `BOOTMAN` is also responsible for loading the appropriate file system drivers or modules to allow the OS to start up.
* Stage 2 (kernel): Kernel loads all necessary drivers, subsystems. Kernel then hands off to initialization binary `init` responsible for starting the userspace.
* Stage 3 (userspace): Userspace loads OS services and eventually loads greeter.
