# Banana PI R2 Pro Getting Started

Steps
- [Requirements](#Requirements)
- [Using Serial](#Using Serial)
- Download OS of Choice
- (Optional) Backing up the EMMC to a USB Drive.
- Flashing to Device
	- SDCard
	- EMMC

## Requirements
### Prerequisites
By using this Getting Started guide, it's assumed that you have the following prerequisites
- Ubuntu 20.04-based Distrobution
- Basic Knoledge of using Linux
- Root access to your machine

### Installing `bpi-tools`
```
$ sudo apt-get update
$ sudo apt-get install -y pv curl bash

$ mkdir bpi-tools; cd bpi-tools;
$ curl -sL https://github.com/BPI-SINOVOIP/bpi-tools/raw/master/bpi-tools | sudo -E bash
```

### Installing `putty`
```
$ sudo apt-get update
$ sudo apt-get install -y putty
```

## Using Serial
I will be using the PL2303 UART to USB Serial Adapter, but any working UART to USB Serial adapter should work fine.

Connect your UART pins to your board, they should be next to the SATA plug. The pins colors should match the following;
- Black -> `GND`
- Green -> `RXD`
- White -> `TXD`

![[img/20220521_163325.jpg]]

Open putty as root by doing `sudo putty` in your terminal, this window should open.![[img/Screenshot from 2022-05-21 16-17-59.png]]

When putty has opened, select the `Serial` radio button and select the `Connection->Serial` option on the left side of the window.

Set the `Serial Line` option to the `tty` path of your serial device. For me, this will be `/dev/ttyUSB0`.

Set the Speed to `1500000`, Data bits to `8`, Stop bits to `1`, Pairity to `none`, and Flow control to `none`.

![[img/Screenshot from 2022-05-21 16-21-09.png]]

Once you've entered your settings, select the `Session` category and save your changes under any profile name, I suggest setting the profile name as `bpi-serial`.

![[img/Screenshot from 2022-05-21 16-21-25.png]]

Now you can connect by pressing the `Open` button on the bottom right of the window.

## OS of Choice
When flashing to the Banana PI R2 Pro you have 3 official options to use. Ubuntu 20.04, Debian 10, and OpenWRT 21.02.

In this guide I will be flashing Ubuntu 20.04 to a 16GB SDCard.

Downloads can be found on the [Resources Page](Resources.md# Banana PI R2 Pro).