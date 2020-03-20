# AtkDongle
AtkDongle is an Open Hardware dongle to test and troubleshoot parallel and serial ports on Amiga Computers.

![Board](https://raw.githubusercontent.com/SukkoPera/AtkDongle/master/img/render-top.png)

### Summary
While diagnosing faults on Amiga computers, it is necessary to connect a loopback adapter to the serial and parallel ports, which might not be easily available. It might also be necessary to check if the power rails are in order, which involves using multimeter probes directly on the port pins with the risk of creating short-circuits that can damage the machine.

AtkDongle was designed to make these operations easier and safer. It was originally made according to the instructions found in keirf's [Amiga Test Kit](https://github.com/keirf/Amiga-Stuff) (previously known as *SysTest*), but later it was found that Chucky's [DiagROM](http://www.diagrom.com) requires the same connections, thus it is compatible with both of these diagnostic tools.

### Assembly
Solder all components to the board in the order you prefer. Just pay attention to use ports of the right gender on each side, as both connectors are D-Sub 25 pins (*DB-25*) but:
- The **parallel** side needs a **male** connector
- The **serial** side needs a **female** connector

You are also recommended to pay attention to the resistors as you might need to tune them according to the colors and type of leds you are going to use: for instance, I used a red, a yellow and a green led and I had to use resistors of respectively 470, 680 and 220 ohm in order to make them look as bright as each other. Cathode (shorter leg) goes into the square pad.

### Usage
You can plug the dongle into the serial or parallel port of any Amiga at any time. Always use one side at a time: **NEVER connect both ports of the dongle at the same time!**

Some of the leds will light up if the power pins are providing voltage and current. In particular:
- D1 should light up when you connect the dongle to the **parallel** port and the 5V rail is getting power.
- D2 and D3 should light up when you connect the dongle to the **serial** port and the +/-12V rails are getting power, respectively.

A led lighting up does not imply that the corresponding voltage is actually correct, so you should grab your multimeter and make sure by measuring on the exposed pads. Just be careful not to trigger any short-circuit (The +12V pad sits pretty close to a leg of R1, you were warned!).

The dongle also provides loopback connections for both the parallel and serial ports. These are useful for the port tests in Amiga Test Kit (hit <kbd>F8</kbd>) or DiagROM (Go to *Porttests*, <kbd>5</kbd>).

Finally, you can solder pin headers that will allow easy access to all the voltages present on the ports so that you can use them to power other boards/peripherals. Note that most (if not all) Amiga models limit the current that can be drawn from the ports, so you are recommended to check the Amiga schematics and **NOT to use these if you do not fully understand what you are doing, as you might damage your Amiga and/or power supply. Also DO NOT connect jumper caps on these pins, they are not meant for that!**.

### Releases
If you want to get this board produced, you are recommended to get [the latest release](https://github.com/SukkoPera/AtkDongle/releases) rather than the current git version, as the latter might be under development and is not guaranteed to be working.

Every release is accompanied by its Bill Of Materials (BOM) file and any relevant notes about it, which you are recommended to read carefully.

### License
The AtkDongle documentation, including the design itself, is copyright &copy; SukkoPera 2020.

AtkDongle is Open Hardware licensed under the [CERN OHL v. 1.2](http://ohwr.org/cernohl).

You may redistribute and modify this documentation under the terms of the CERN OHL v.1.2. This documentation is distributed *as is* and WITHOUT ANY EXPRESS OR IMPLIED WARRANTIES whatsoever with respect to its functionality, operability or use, including, without limitation, any implied warranties OF MERCHANTABILITY, SATISFACTORY QUALITY, FITNESS FOR A PARTICULAR PURPOSE or infringement. We expressly disclaim any liability whatsoever for any direct, indirect, consequential, incidental or special damages, including, without limitation, lost revenues, lost profits, losses resulting from business interruption or loss of data, regardless of the form of action or legal theory under which the liability may be asserted, even if advised of the possibility or likelihood of such damages.

A copy of the full license is included in file [LICENSE.pdf](LICENSE.pdf), please refer to it for applicable conditions. In order to properly deal with its terms, please see file [LICENSE_HOWTO.pdf](LICENSE_HOWTO.pdf).

The contact points for information about manufactured Products (see section 4.2) are listed in file [PRODUCT.md](PRODUCT.md).

Any modifications made by Licensees (see section 3.4.b) shall be recorded in file [CHANGES.md](CHANGES.md).

The Documentation Location of the original project is https://github.com/SukkoPera/AtkDongle/.

### Support the Project
Since the project is open you are free to get the PCBs made by your preferred manufacturer, however in case you want to support the development, you can order them from PCBWay through this link:

[![PCB from PCBWay](https://www.pcbway.com/project/img/images/frompcbway.png)](https://www.pcbway.com/project/shareproject/AtkDongle_V1.html)

You get my gratitude and cheap, professionally-made and good quality PCBs, I get some credit that will help with this and [other projects](https://www.pcbway.com/project/member/shareproject/?bmbid=41100). You won't even have to worry about the various PCB options, it's all pre-configured for you!

Also, if you still have to register to that site, [you can use this link](https://www.pcbway.com/setinvite.aspx?inviteid=41100) to get some bonus initial credit (and yield me some more).

Again, if you want to use another manufacturer, feel free to, don't feel obligated :). But then you can buy me a coffee if you want:

<a href='https://ko-fi.com/L3L0U18L' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi2.png?v=2' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

### Get Help
If you need help or have questions, you can join [the official Telegram group](https://t.me/joinchat/HUHdWBC9J9JnYIrvTYfZmg).

### Thanks
- [keirf](https://github.com/keirf) for Amiga Test Kit
- Chucky for DiagROM
