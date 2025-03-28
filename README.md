# rae-dux guide and config
The rae-dux is a wireless ergo split keyboard designed by
[Andrew Rae](https://github.com/andrewjrae/). I built with the help of this
[rae-dux-guide](https://www.tzcl.me/posts/rae-dux/)[^1]. This
[blog](https://hackaday.io/project/187234-rae-dux-keyboard-build) can also
be really helpful. Thanks to a friend of mine that inspired me with
[his build](https://github.com/haglobah/zmk-config-tzcl). If you have a question
don't hesitate to write an issue.

![rae-dux-justsamagain](https://github.com/user-attachments/assets/f78e2e05-ac88-48d8-a092-7bcfa1650849)

This repo is not meant to be a full guide as the mentioned guide is really good
and I don't want to copy it [^1].
It is intended to be an extension as there were a few things in the guide that
were (at least for me) not 100% clear and I did a few things a bit different
(e.g. different controller). <br>
That means this repo is mostly be a small, more detailed [collection](#build-guide)
of the components you need, the files and links (and shops) I used and a [guide
for building your own configs](#configuring-zmk) as that was not explained
in the guide at all. <br>
So first visit the mentioned guide and if some things are unclear there or you want
to know if I did smth differently then come back. :)

[^1]:Not available anymore? Please tell me - then I'll write my own.

## build guide
[rae-dux-guide](https://www.tzcl.me/posts/rae-dux/)[^1]
### the PCBs (min 2x)
First I had the **pcbs** printed. For that I used the
[gerber file by andrewjrae](https://github.com/andrewjrae/rae-dux/blob/rae-dux/output/gerber.zip)
and sent them to JLCPCB. I chose them as they are really cheap and easy, but
depending on where on the world you are you might have to wait a while for the
pcbs to arrive. When I ordered the pcbs, I chose lead free ones as one always
interacts physically with the boards. (for more information about the whole
process, see the mentioned guide ;))
<details>
  <summary>alternative rae-dux-pcb files</summary>
  There are also some alternative rae-dux-pcb files. One is the
  [goos-rae-dux-board](https://github.com/FelixBrgm/goos) by
  [FelixBrgm](https://github.com/FelixBrgm). He moved the pads for the switches
  further apart so the [wrk. louder mx sized keycaps](https://worklouder.cc/shop/wrk-blind/)
  would fit. **But take care, the moment I write this he advises in his README
  against using the pcb files as there were some issues with them.**
</details>

### the components and where I ordered them
**The controllers** (min 2x):<br>
Originally a nice!nano is used for the boards, but as they are quite expensive I
used the 'SuperMini NRF52840' and ordered them from AliExpress. They worked for
me exactly the same as the original ones.
([the repo that helped me finding the board](https://github.com/joric/nrfmicro/wiki/Alternatives))<br>
I've ordered all the other components (but the keycaps, see later on) from
splitkb.com or AliExpress.<br>
Some information concering that:
- 2x 3.7V (200mAh) **LiPo battery**: shouldn't be lager than ... x ... x ...
- 2x right-angle **JST-2 connector**: The pin distance of the JST connectors I
used is ...
- 4x 13x **female machined pin headers**: The pin distance on the board and
controller is ..., so you will need sockets with that spacing. I ordered rows of
40 pins each and broke then into rows of 13 pins.
- 56x **mill-max pins**: I ordered these on
[splitkb](https://splitkb.com/products/mill-max-low-profile-sockets?variant=32170972020813)
because it turned out to be a bit difficult to find the exact properties of the pins.
- 2x **reset button**: dimensions should be 6x3x4.3mm, I used ones from AliExpress
- 2x **power switch**: 7 pins, you can see the dimensions [here](https://keebd.com/products/switch-mini-7-pin-2-slide-positions)
- 36x **kailh low-profile hotswap sockets**: use the choc ones, they are a bit 8-shaped,
with the dimensions 4.7x13.2x1.8mm. (e.g. [these would work](https://splitkb.com/products/kailh-hotswap-sockets?variant=39472161456205))
- 36x **low profile choc switches**: I used the ones from [splitkb](https://splitkb.com/products/kailh-low-profile-choc-switches?variant=33100108234829)
but you can find these all over the web. Just think about your typing preferences.
Do you want them to by hard and clicky or light and silent.
Order the ones that fit your need :) (Hint: The higher the gf-value, the harder they
are to press)
- 36 x **choc keycaps**: [I 3d-printed these](#3d-printing-the-choc-keycaps),
however, you can order them easily on the web, just take care they have a maximum
size of 17.5x16.5mm, the ones I printed are 15x15mm.
- **rubber feet** can be useful

<details>
  <summary>Planning to order from splitkb.com? Then pay attention to this 👇</summary>
  Take care if you decide to order the hotswap sockets for the nice!nanos from
  splitkb.com. They have (as I am writing this) one pin too few for the controllers
  (12 instead of 13). But if you don't plan on building whireless boards that won't
  be a problem for you as these two pins are only used for charging and discharging the
  battery.
</details>

### Building the Boards
The assembly of the boards is pretty well explained in the
[guide](https://www.tzcl.me/posts/rae-dux/), so I will not further expand on that.

#### 3d-printing the choc keycaps

What is worth mentioning are the keycaps. I printed them with our home 3d
printer. For that I used [3d files](https://www.printables.com/model/1069263-15x15-minimal-spaced-kailh-choc-keycap)
from printables.com and modified them to have some homing caps.
You can find them in this repo [here](3d-files). <br>
They turned out really well with PLA (the black caps in the image).
PETG (the blue ones) was also not bad, but PLA was better.<br>

I also tested the following files, but had some issues with each of them:
- [3d files of the wrk. louder caps](https://www.printables.com/model/685983-kea-profile-choc-v1-keycaps-mx-spaced),
they are MX sized and thus too large
- [smaller louder keycaps](https://www.printables.com/model/1066117-choc-louder-keycaps-choc-and-mx-spacing),
the small ones barely fit but I found them to be too clunky for me

<details>
  <summary>Some funny key caps 3d-files</summary>
  - [round ones](https://cults3d.com/en/3d-model/gadget/kailh-choc-v1-modular-keycaps) (not tested)
  - [duck key cap](https://www.printables.com/model/911964-kailh-choc-custom-duck-keycap) (not tested)
</details>


### Configuring ZMK
*! currently in work !*

That's the part where I found the guide to be really confusing. The .uf2 files
are not that easy to find. <br>
I downloaded the .uf2 files from the [repo by haglobah](https://github.com/haglobah/zmk-config-tzcl)
(but there are a few alternatives e.g. [the config of FelixBrgm](https://github.com/FelixBrgm/goos)).
They are quite well hidden if you are not used to GitHub. If you know GitHub,
they are in the build artifacts of the build job under GitHub Actions. For
everyone else, here is the longer explanation: You can find them if you go on
his [repo](https://github.com/haglobah/zmk-config-tzcl) and click on 'Actions'
in the naviagtion bar. Then select 'Build' on the left, click on the latest
workflow run and scroll down until you see the 'Artifacts'. There you need to
download the 'firmware'. That's the zip folder containing the .uf2 files.

If you want to compile your own configs you have to follow the [explanation of
the zmk project](https://zmk.dev/docs/user-setup). I just did that and it Was
reallly complicated for this keyboard.

The easier way is to fork my repo and open it with the
[Keymap editor](https://nickcoutsos.github.io/keymap-editor/)
made by Nick Coutsos. <br>
Otherwise you can select Clipboard, select custom and use the .json file
in this repo and make your own configs.

#### Storage box
If you want to print your own storage box for the board, here is a
[repo](https://github.com/haglobah/rae-dux-case) that contains a 3d-file for one
that closes using magnets. I am currently also building my own with a sliding
mechanism.
