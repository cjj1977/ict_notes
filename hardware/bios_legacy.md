# Legacy BIOS

## About

Legacy BIOS is the boot process used by BIOS firmware, which stores a list of
bootable devices installed on your PC on a priority order. When the computer is
powered on, the BIOS performs [Power On Self-Test (POST)](./post.md). Once done,
the firmware will load the first sector of each storage target into memory and
scan it for a valid MBR.

If it is found, the firmware will pass execution to the boot loader code in MBR
that enables users to select a partition to boot from. If no valid MBR is found
on the current device, it will proceed to the next one in the boot order. If no
valid MBR is found on all installed bootable devices, the Windows cannot boot.
