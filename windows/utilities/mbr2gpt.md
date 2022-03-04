# MBR2GPT.EXE

## Usage

```cmd
MBR2GPT /validate|convert [/disk:<diskNumber>] [/logs:<logDirectory>] [/map:<source>=<destination>] [/allowFullOS]
```

1. Open an elevated command prompt.
2. Copy and paste the `mbr2gpt /convert /allowfullOS` command into the elevated
command prompt, and press Enter.
3. When the conversion has successfully completed, you will need to boot to UEFI
firmware settings, and switch the firmware to boot to UEFI mode instead of
Legacy BIOS (CSM).

-- [tenforums.com](https://www.tenforums.com/tutorials/81502-convert-windows-10-legacy-bios-uefi-without-data-loss.html)

## About

MBR2GPT.EXE converts a disk from the Master Boot Record (MBR) to the GUID
Partition Table (GPT) partition style without modifying or deleting data on the
disk. The tool is designed to be run from a Windows Preinstallation Environment
(Windows PE) command prompt, but can also be run from the full Windows 10
operating system (OS) by using the /allowFullOS option.

-- [docs.microsoft.com](https://docs.microsoft.com/en-us/windows/deployment/mbr-to-gpt)

## Notes

* While the tool supports being run from Windows 10, there are recommendations
to run it from a [Windows PE](./winpe.md) environment.
* Although disks configured with MBR-style partition can have up to four primary
partitions, for this process to work the disk you want to convert can't have
more than three partitions, because one allocation is needed to create the new
UEFI system partition.

* See [UEFI Bios](/hardware/bios_uefi.md)