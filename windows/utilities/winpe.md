# Windows Pre-installation Environment

## Usage

1. Install the [Windows Assessment and Deployment Kit (ADK)](./adk.md)
2. Open the **Deployment and Imaging Tools Environment**
3. Copy the Windows PE environment to a working folder, e.g. `S:\WinPE_amd64`:

```cmd
copype amd64 S:\WinPE_amd64
```

4. [Create a bootable USB drive](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive)

```cmd
makewinpemedia /ufd s:\winpe_amd64 F:
```

## About

Also known as Windows PE or WinPE, it is a lightweight operating system with
limited features. Mostly, it is used to install, deploy, and repair Windows for
desktop editions, including Windows 10, Windows Server, and other Windows
operating systems.

From Windows PE, you can:

* Set up your hard drive before installing Windows.
* Install Windows by using apps or scripts from a network or a local drive.
* Capture and apply Windows images.
* Modify the Windows operating system while it's not running.
* Set up automatic recovery tools.
* Recover data from unbootable devices.

-- [docs.microsoft.com](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-intro)
