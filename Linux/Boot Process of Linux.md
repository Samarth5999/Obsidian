## BIOS/UEFI
* When power button is pressed, it starts a program called the BIOS (Basic Input Output System) or UEFI (Unified Extensible Firmware Interface). 

| BIOS                                                                               | UEFI                                                                                    |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| BIOS is tied to the Master Boot Record(MBR) system, which limits disk size to 2 TB | UEFI uses GUID Partition Table (GPT), removing the size constraints and modern solution |
| Slower boot time                                                                   | Faster boot time                                                                        |
| Less secure boot                                                                   | Secure boot                                                                             |
* BIOS or UEFI runs a check called Power ON Self-Test (POST). This check make sure all the bits and pieces are working before turning everything on.
* BIOS then searches for a bootable device, then loads and executes the first stage of the boot loader, which is stored in the MBR (Master Boot Record) of that device.

## Master Boot Record (MBR)

* It is just a sector (first 512 bytes) on the disk.
* It contains the primary bootloader code (usually 446 bytes) plus the partition table.
* When BIOS hands control to the MBR, the bootloader code there runs — typically it loads GRUB.

## Bootloader

The key job for the boot loader are:- 
1. Locate the OS kernel on the disk.
2. Load the kernel into the computer's memory.
3. Start running the kernel code.

* The most advanced bootloader used nowadays is Grand Unified Bootloader (GRUB).
* GRUB configuration file is `/boot/grub/grub.conf`.

## Kernel

After the bootloader starts the kernel, the kernel takes over the computer's resources and starts initiating all the background processes and services.

* The Kernel initializes hardware, sets up essential system components, loads and mounts the root filesystem, and uses `initrd` as a temporary root filesystem containing the drivers and tools required to mount the actual root filesystem.
* It executes `init` or `systemd` (modern systems) which is the first process in the user space with a PID 1.
* From here, the kernel's job shifts from booting to managing the running system.

## Init

* Init reads the file `/etc/inittab`, this file tells init which runlevel the system should boot into i.e init sets the runlevel — which decides what services and processes should start.

| Runlevel |                Mode                |
| :------: | :--------------------------------: |
|    0     |          Halt (Shutdown)           |
|    1     |          Single User Mode          |
|    2     |    Multi-User Mode (No Network)    |
|    3     | Multi-user (Networking but no GUI) |
|    4     |               Unused               |
|    5     |       Multi-User Mode (GUI)        |
|    6     |               Reboot               |
* Init runs scripts located in directories like: `/etc/rc.d/rc*.d` or `/etc/init.d/` depending on the chosen runlevel.

After all services are up, init spawns getty processes on terminals to display login prompts (text or GUI).