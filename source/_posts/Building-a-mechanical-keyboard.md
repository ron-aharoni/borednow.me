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

### Designing a layout

Due to the keyboard being a 60% keyboard, and missing some keys, several layers are needed. Here are my layers for the Nyquist:
</br>
<img style="display: inline;" src="/images/layout.png">

### Flashing the firmware

The hardest part was surprisingly flashing the firmware, which is why I decided to document it here.
1. [Install](https://beta.docs.qmk.fm/tutorial/newbs_getting_started) qmk
2. Build your keymap on [https://config.qmk.fm/](https://config.qmk.fm/)
3. Download the keymap json and save it in the qmk_firmware folder (the qmk installation location).
4. Generate the firmware by running the following command:
```bash
$ qmk compile mylayout.json
```
This copies the firmware into qmk's firmware folder.
5. Reset your keyboard.
6. Flash the firmware:
```bash
$ sudo make keebio/nyquist/rev3:mylayout:flash
```

### The end result
As you can see I had to be creative with some keycap labels, but more are on the way :)
![keyboard](https://i.imgur.com/NH5PHFm.jpeg "keyboard")
![keyboard](https://i.imgur.com/UV98sj3.jpeg "keyboard")
![keyboard](https://i.imgur.com/RQDljq4.jpeg "keyboard")