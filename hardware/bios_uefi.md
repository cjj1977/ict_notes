# UEFI

## About

UEFI Boot is the abbreviation of Unified Extensible Firmware Interface. It is
considered as the successor to the [Legacy BIOS](./bios_legacy.md).

The firmware in UEFI boot keeps a list of valid boot volumes called EFI service
partitions. During the POST procedure, the UEFI firmware will scan all the
bootable storage devices on your machine for a valid GUID Partition Table (GPT)
and find an EFI service partition to boot from.

If it does not find any EFI boot partition, the firmware will be back on the
Legacy BIOS boot method. If both methods don’t work, the Windows will fail to
boot up.

-- From [diskpart.com](https://www.diskpart.com/windows-10/convert-windows-10-from-legacy-bios-to-uefi-without-data-loss-7201.html)

## Notes

### Converting to UEFI

* In order to convert from Legacy BIOS to UEFI, you need to upgrade your
partitions to have a GPT rather than MBR.
* Typically this means re-creating the partition and re-installing the OS
* 3rd party tools may be able to convert existing partitions *in-situ*.

#### MBR2GPT.EXE

Starting in Windows 10 version 1703 build 15063, you can use the MBR2GPT.EXE command line tool to convert a disk from Master Boot Record (MBR) (used in Legacy BIOS) to GUID Partition Table (GPT) (used in UEFI) without having to clean install Windows 10 or modifying or deleting data on the disk. The tool is designed to be run from a Windows Preinstallation Environment (Windows PE) command prompt, but can also be run from the full Windows 10 operating system (OS).

* See [MBR2GPT.EXE](../windows/commands/mbr2gpt.md)