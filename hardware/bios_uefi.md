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

* [diskpart.com](https://www.diskpart.com/windows-10/convert-windows-10-from-legacy-bios-to-uefi-without-data-loss-7201.html)

## Notes

### Converting to UEFI

* In order to convert from Legacy BIOS to UEFI, you need to upgrade your
partitions to have a GPT rather than MBR.
* Typically this means re-creating the partition and re-installing the OS
* 3rd part tools may be able to convert existing partitions *in-situ*.
