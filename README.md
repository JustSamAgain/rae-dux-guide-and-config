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
(e.g. [different controller](#the-components-and-where-I-ordered-them)). <br>
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
- 2x 3.7V (200mAh) **LiPo battery**: shouldn't be lager than 12.5x33x4mm
- 2x right-angle **JST-2 connector**: The pin distance of the JST connectors I
used is 2mm. (I used [these](https://splitkb.com/products/wireless-controller-expansion-bundle?variant=42344261288195))
- 4x 13x **female machined pin headers**: The pin distance on the board and
controller is 2.54mm, so you will need sockets with that spacing (I used
2.0x2.54mm ones). I ordered rows of 40 pins each and broke then into rows of 13
pins.
- 56x **mill-max pins**: I ordered these on
[splitkb](https://splitkb.com/products/mill-max-low-profile-sockets?variant=32170972020813)
because it turned out to be a bit difficult to find the exact properties of the pins.
- 2x **reset button**: dimensions should be 6x3x4.3mm, I used ones from AliExpress
(should look like [these](https://keebd.com/products/3x6x4-3mm-dip-push-button-switch))
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

### Flashing the keyboard
That's the part where I found the guide to be really confusing. The .uf2 files
are not that easy to find. <br>
You can download my config files from this repo. <br>
As I am using a german layout I set up **two layout branches**. There are 
the **german-layout**[^2] and the **us-layout** branch. The reason for that 
is that the ZMK's key codes indicate the position of a key on a US keyboard 
layout, not the key's function ([source](https://github.com/joelspadin/zmk-locales)).
So if you are not using the us-qwerty keyboard on your computer, the 
zmk-layout may act weird.<br>
Therefore if you are using either the german or us layout you can go on 
with the next paragraph and download my german or us config. If you are 
using a different language or don't like my layout you need to 
[configure your own layout](#configuring-zmk) as I currently only 
support the mentioned ones.

Nice! You decided to give one of my layouts a shot. Choose the branch 
you decided to take on the top of the page (click on the branches button 
and then select the german or us branch). Here you can see all the config files.<br>
Now click on 'Actions' in the navigation bar. Then search for the 
latest workflow run fitting your chosen language. (if you don't want to 
search, you can also select on the right side of the bar above the workflows 
'Branch' and set a filter for the branch you have chosen)
Select it and scroll down until you see the 'Artifacts'. There you need to 
download the 'firmware'. That's the zip-folder containing the .uf2 files.

For flashing your boards connect them via cable with your computer and 
click two times on the reset button to put them into boodloader mode. 
They should then show up on your computer and be mountable like a 
USB-drive. Grab the correct .uf2 file and drop it into the filesystem 
of the controller. After this it should reboot and eject itself.
Now they should already work via cable.<br>
Pair your device with the boards via Bluetooth to use them wirelessly.

<details>
  <summary>If you want a different layout, here are some</summary>

  You can find the .uf2 files here in the same location as described above.
  - [repo by haglobah](https://github.com/haglobah/zmk-config-tzcl)
  - [the config of FelixBrgm](https://github.com/FelixBrgm/goos)
</details>

<details>
  <summary>german-layout explained</summary>
  
  I have chosen to use a colemak layout - that's why the key layer isn't 
  similar in any way to the layout you are probably used to.
  ![image](https://github.com/user-attachments/assets/c6b90df1-9429-44b7-b8a6-2e052ebf2a7e)<br>
  This is my base layer. On the middle row you can see that there are weird double signs.
  That is what we call 'home row mods'. If you hold the \<a\> (or \<o\>) key on the left, it won't type an
  'a' but get interpreted as you holding the left \<alt\> key. The same goes with the other 
  keys that have two labels on them: the \<r\> and \<i\> works when you hold it as \<GUI-key\> (on windows 
  that's the win-key), the \<s\> or \<e\> as \<Shift\>, the \<t\> or \<n\> as \<Strg\>. 

  While holding the thumb keys you can switch to different layers.<br>
  To switch to the symbol layer you need to hold one of the middle thumb
  keys (they are on both sides the same, just mirrored).
  ![image](https://github.com/user-attachments/assets/4048155c-dadc-4822-9ecb-58b2b72d7672)

  You can switch to the num-layer while pressing the inner thumb keys:
  ![image](https://github.com/user-attachments/assets/88af6aad-e115-407f-8a28-bcab9ecb298c)

  And to the nav-layer while holding down the outer thumb keys:
  ![image](https://github.com/user-attachments/assets/90fced65-cea7-4fcc-8de8-ddf9ae0ee548)

  That's not all, as you might have realized, you cannot type every sign 
  yet (like for example a question mark).<br>
  For that I am using something that we call 'combos'.
  ![combos](https://github.com/user-attachments/assets/5017a4e0-a3cd-4846-b73f-c912361ca419)<br>
  There are some that are not really useful, my plan is to look what I really need and 
  replace them in future.
</details>

<details>
  <summary>us-layout explained</summary>

  I have chosen to use a colemak layout - that's why the key layer isn't 
  similar in any way to the layout you are probably used to.
  ![image](https://github.com/user-attachments/assets/ccc29082-8ac0-4459-8d09-6344e12c7400)<br>
  This is my base layer. On the middle row you can see that there are weird double signs.
  That is what we call 'home row mods'. If you hold the \<A\> (or \<O\>) key on the left, it won't type an
  'A' but get interpreted as you holding the left \<ALT\> key. The same goes with the other 
  keys that have two labels on them: the \<R\> and \<I\> works when you hold it as \<GUI-key\> (on windows 
  that's the win-key), the \<S\> or \<E\> as \<SHIFT\>, the \<T\> or \<N\> as \<CRTL\>.

  
  
  While holding the thumb keys (currently only the middle one) you can switch to different layers.<br>
  To switch to the num-layer you need to hold one of the middle thumb
  keys (they are on both sides the same, just mirrored).
  ![image](https://github.com/user-attachments/assets/51caaa77-e81f-42ed-8476-4fbbfd412fdc)

  That's not all, as you might have realized, you cannot type every sign 
  yet (like for example a question mark).<br>
  For that I am using something that we call 'combos'.
  ![combos-us](https://github.com/user-attachments/assets/db03b2ef-84af-4ba6-86e3-c945e2aa0c1e)<br>
  There are some that are not really useful, my plan is to look what I really need and 
  replace them in future.<br>
  Note: This layout is currently probably more sort of a good starting point for learing
  and then configuring to the own needs.
</details>

<details>
  <summary>How to learn the new layout? ;)</summary>

  Learning the new layout can take a bit of efford. But dont give up :)
  Here are some websites that really halped me getting into it:

  - https://www.keybr.com/
  - https://monkeytype.com/?lang=en<br>
  And finally: simply practice, learn the basics so you can "survive"
  using the board and then start using one shortcut, one special character
  after another.
</details>

[^2]:heavily inspired by the [layout haglobah uses](https://github.com/haglobah/zmk-config-tzcl)

### Configuring ZMK

If you want to compile your own configs I would recommend you to fork this
repository (button on the top right of this page) and open it in 
the [Keymap editor](https://nickcoutsos.github.io/keymap-editor/) made by Nick Coutsos.
You can edit there your configs graphically and push it back into the repository.
Just choose the right branch you want to work on (main, german or us-layout as 
explained before) and adjust it to your needs.

If you aren't using a german or US keyboard layout you will soon see that either your keys 
are not in the Keymap editor or your system thinks you are tapping different buttons. If so 
you may have to do some extra work:

Either you go into your settings and switch your layout to the US layout while using
the keyboard (in that case I would recommend you to work on the us-layout branch).

Or, and this is my preferred way: Go to [zmk-locale-generator](https://github.com/joelspadin/zmk-locale-generator/releases),
download your language package (in the german case that was `keys_de.h`) and copy it to the "config"
folder. Then open the rae_dux.keymap file and add the file to the imports (in the german case that's
`#include "keys_de.h"`). It's best if you use the main branch for that as you can build your
configs there from ground up and the language file wouldn't interfere with e.g. the german file.
But you can of course use the german branch as example how to configure the language stuff.

Downloading your newly built firmware exactly works like described [above](#flashing-the-keyboard). 
The only difference is that you download the files from your own repo now instead of mine.

If you are interested in the whole ZMK Framework you can read and follow the [explanation of
the zmk project](https://zmk.dev/docs/user-setup). However, I wouldn't recommend the setup for 
this keyboard. It was reallly complicated as this board unfortunately is too unpopular and therefore 
not officially supported.

As always, if you have any problems with the explanation, please don't hesitate to 
open an Issue. :)

#### Storage box
If you want to print your own storage box for the board, here is a
[repo](https://github.com/haglobah/rae-dux-case) that contains a 3d-file for one
that closes using magnets. I am currently also building my own with a sliding
mechanism.
