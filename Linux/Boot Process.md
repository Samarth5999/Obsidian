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

After GRUB loads up, it inserts the Linux kernel into  memory and hands control over to the kernel to finish the startup process. 