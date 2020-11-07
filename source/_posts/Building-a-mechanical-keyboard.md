---
title: Building a mechanical keyboard
tags:
  - split
  - mechanical keyboard
date: 2020-11-07 20:52:43
---


A friend recently told me he ordered parts for a split mechanical keyboard.
I have been using a split keyboard for several years (the [Kinesis Freestyle 2](https://kinesis-ergo.com/shop/freestyle2-for-pc-us/)) and like the experience. I was looking for a new split, this time a mechanical keyboard, but it seemed all good options (that is, without awkward [thumb keys](https://ergodox-ez.com/)) are custom builds. So I jumped on the opportunity to build one with him.

### Parts

I ordererd the following:
* Nyquist 60% ortholinear PCB and plates from [keeb.io](keeb.io)
* Cherry Brown switches
* DSA keycaps from [pimpmykeyboard.com](https://pimpmykeyboard.com/dsa-standard-sublimated-keysets/)
* Fancy TRRS and [USB-C](https://kprepublic.com/products/textile-jean-cloth-usb-c-micro-cable-type-c-usb-1-6m-stright-length-blue-colorway?_pos=9&_sid=f199e67bf&_ss=r) cables

The assembly process, with the help of my friend, was pretty simple. We installed the space bar stabilizers, soldered the switches and assembled the top and bottom plates.

### Flashing the firmware

The hardest part was surprisingly flashing the firmware, which is why I decided to document it here.
1. [Install](https://beta.docs.qmk.fm/tutorial/newbs_getting_started) qmk
2. Build your keymap on [https://config.qmk.fm/](https://config.qmk.fm/)
3. Download the keymap json and save it in the folder appropriate for your keyboard type.
4. Generate `keymap.c` by running the following command, replacing the folder and layout name:
```bash
$ make keebio/nyquist/rev3:mylayout
```
This copies the firmware into qmk's firmware folder.
5. Press your keyboard's reset button.
6. Flash the firmware by running the following. Again replace folder and layout name.
```bash
$ sudo make keebio/nyquist/rev3:mylayout:flash
```

### The end result

![The keyboard](IMG_20201023_195103.jpg)
![At work](IMG_20201024_104204.jpg)
![Leds](IMG_20201024_104208.jpg)