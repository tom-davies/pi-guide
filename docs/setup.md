# Raspberry Pi Setup

---

**WARNING:** This guide assumes that you will be using your Raspberry Pi headless (without a screen, keyboard or mouse) and connecting to it from a Windows 10 PC. If this is not the case, you may need to alter some of the steps to suit your particular setup.

---

## SD Card Creation

Download the Raspberry Pi Imager from [raspberrypi.org](https://www.raspberrypi.org/downloads/). Once that is downloaded and installed, follow the instructions in the app to create or "flash" your SD card with *Raspberry Pi OS Lite*.

## SSH

To enable a headless setup with SSH access, create a file called ```ssh``` with no file extension at the root of the SD card. The file does not have to contain anything. This file instructs the Raspberry Pi to start an SSH server when it is first powered on.

Once this SSH Server is running, you will will be able to access the Raspberry Pi from another computer on the same network, by inputting the command ```ssh raspberrypi.local``` in PowerShell.
