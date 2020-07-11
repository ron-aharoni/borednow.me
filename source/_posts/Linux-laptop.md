---
title: Linux laptop
date: 2020-07-10 22:16:30
tags:
- Linux
- Development
- Manjaro
---

I recently purchased a laptop. My requirements were a HiDPI screen for photo editing, 16GB of RAM and a CPU that is suitable for development (not only of the Node.js full stack variety).

I considered an MBP, but used MacBook's have horrible keyboard or are too old, and newer ones cost alot. With macs out of the picture, I considered Lenovo, Dell, and Asus, and my budget was up to 1300USD. A refurbished or used thinkpad would have answered all the requirements, except for the screen, and they also have old propietary charging connectors which are annoying if you're used to USB C.

After much consideration I settled on a [Lenovo IdeaPad S540-IML](https://www.lenovo.com/il/en/laptops/ideapad/s-series/Lenovo-IdeaPad-S540-13IML/p/88IPS501379).
Being a consumer Laptop, I was worried about Linux compatibility, but the specs and price were too good to pass up:
* 10th Gen Intel Quad Core i5-10210U CPU @ 1.60GHz, up to 4.2 GHz
* 16GB DDR4 2666MHz (soldered, non upgradable)
* 1TB M.2 2280 SSD PCIe NVMe
* 13.3 Inch QHD (2560 x 1600)
* NVIDIA GeForce MX250, with 2GB GDDR5 VRAM (optional, but doesn't add much to the price)
* 2 x USB 3.1 Type-C
* 1 x USB 3.1 Type-A (Gen 1)
* ~1.4 KG

The plan was to dual boot Windows 10, which will be used for casual gaming and photo editing, and linux for development.

## Choosing a distro
In the past I used Ubuntu, Debian, Mint (both the Ubuntu and Debian based editions), Fedora and most recently Arch linux. I also heard about PopOS so I thought to give it a try as well.

I created a PopOS live USB, and the system looked good, but had a freezing issue. Perhaps it would have been solved by installing updates, but I didn't check. Other than that everything worked which encouraged me.

I later tried linux mint, which failed to detect the Wi-Fi card. It was also slow compared to PopOS, which I think was down the the desktop environment (Cinnamon vs Gnome for PopOS).

The third system I tried, and the one I stuck to was Manjaro gnome edition. I like arch, but wanted something easier as this will be my main system.

## Installation steps

The main deliberation here was partitioning. Since I want to dual boot with Windows 10. Most reccommend disabling Secure Boot and fast boot. Before disabling them my system didn't boot from the live USB.
After disabling them, I shrank the Windows partition to half its size.
I booted into the Manjaro live USB, and started the graphical installer.
There are conflicting articles about whether to use one or two UEFI boot partitions. I opted to leave the Windows boot partition as is and create a different one for Manjaro as it seems that this has less change of conflicts if Windows decides to change something in the boot partition.
This is the final partition layout:
  |             Type             	|   Size   	|       Role       	|   Mount   	|
  |:----------------------------:	|:--------:	|:----------------:	|:---------:	|
  |          EFI system          	|  260 MiB 	|   Windows boot   	|           	|
  | Microsoft reserved partition 	|  16 MiB  	|     god knows    	|           	|
  |  Basic Data Partition (NTFS) 	|  451 GiB 	|   Windows data   	|           	|
  |          EFI System          	|  512 MiB 	|    Linux boot    	| /boot/efi 	|
  |           linuxswap          	| 7.91 GiB 	|       Swap       	|           	|
  |             ext4             	|   27.94  	|    Manjaro OS    	|     /     	|
  |             ext4             	|   27.94  	|  Alternative OS  	|           	|
  |             ext4             	|  436 GiB 	|       home       	|   /home   	|
  |             ntfs             	| 1000 MiB 	| Windows recovery 	|           	|

## Post install
Run updates, install chromium, Code OSS (VS Code), 
I like a drop down terminal, and [this](https://extensions.gnome.org/extension/1509/drop-down-terminal-x/) one works well.

## Fixing issues
I encountered two issues, random freezing, which was solved by upgrading the system, and no sound, which was solved as described in the [Arch Wiki page](https://wiki.archlinux.org/index.php/Lenovo_IdeaPad_S540_13IML) I opened for the laptop.

## Installing Scala

Install a JDK (Arch only has OpenJDK) and the sbt package.
I use Visual Studio Code, and the version in the repostiries is the open source one Code OSS.
Install the Metals extension for Code OSS.
Then I had a really weird error when downloading dependencies from sbt. This [solution](https://classicforum.manjaro.org/index.php?topic=236.0) worked.

## Installing Node.js
Install nvm from AUR, then install the latest node version.

It took a day, but in the end I'm really happy with the system.