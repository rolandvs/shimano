# Shimano e-Steps
This repository is dedicated to the Shimano e-Steps as I happen to have an e-Bike that is fitted with the Shimano drive-train. There is hardly any technical information on the electronics, so I decided to do a little exploring myself.

Update: ```31-12-2021``` - Added SC-E6010

## e-Bikes
Electrification of a bike is very populair. There are two basic bike types:

- pedelec, limited to 25km/h, no helmet required
- speed e-bike, limited to 45km/h, requires a helmet, insurance

Among the pedelecs, drive-trains of Bosch, Shimano, Bafang and Yamaha are used as well as automatic transmission systems of Shimano, NuVinci, etc. which make riding a bike a joy.

## Speeding up the e-Bike
Somehow we always are looking to get close or beyond the boundries that are set. In a case of a pedelec it would be interesting to go beyond the 25km/h speed limit. Doubling speed is dangerous, however setting the limit to 28 or 30km/h would be nice.

In the software the circumfence of the wheel is all that needs to be set, but where...


## Documents
You can find some patents in the [patents](patents/) directory.

## Communication
The communication between the different system parts on the e-bike use power line communication (i.e. data is superimposed on the DC voltage).

**`TODO`**<br>

- Hookup oscillocope and see what happens
- Measure voltages on the "bus"

## SC-E6010
The console/display of the e-bike is a graphical display with backlight. It features a display, two buttons, a bus interface and an internal Li-Ion battery. The processor and the proprietary bus for the e-bike seem to be split in a specific IC and a more generic controller from Renesas R5F100GJA.

_Datasheet and photos are in the picture directory._

## Experiments
I ordered a bunch of accessoires and started experimenting...

### Add the EW-WU111
For anyone that thinks that just adding the Bluetooth module to the bike: it doesn't work.

- Connect EW-WU111 to EW-SD50
- Take out any connection on the bike
- Place the interface and cable in between
- Pressing the power button

The display stays clear and the e-steps system does not turn on.

- Restore the situation
- Pressing the power button

The display turns on and the e-steps system works like before.

### Use the SM-PCE1
Let's try to hookup the PC interface. For that we install the software on a PC.

- Preinstall Microsoft `dotnetfx35.exe` software as this is required. You can find this on the Microsoft website.
- Install the Shimano software `e-tube project`. This can be found on the Shimano website.
- Put the **`SM-JC41`** junction box in one of the wires from the e-bike system
- Attach the **`SM-PCE1`** to the USB port
- Attach the special cable to the SM-PCE1 and the other end to the junction box

*Tested on 13-08-2018 with the above setup and the result was that the setup is not working. The setup uses a `Mac`, with `VMWARE` and `Windows 8..10`, to work like a PC. Checking some forums revealed that there are more problems using "other" systems than PC's as people claim that the USB implementation of the SM-PCE1 does not comply with the USB standard.*

**`NOTE:`** So the next step is to find a PC and repeat the above process.

So far all experiments turned up nothing and are a bit frustrating. 


## Accessoires

### SM-PCE1 PC Linkage Device
The `SM-PCE1` is an USB interface to connect the e-Steps system to a PC. It is used for service, configuration and maintenance. It is normally not required for a bike owner to have such an interface, but my curiosity was triggered to find out if I can hookup Bluetooth to my bike.

Refer to the [pictures](pictures/) directory and look for all pictures that start with the prefix `SM-PCE1`.

#### Super Capacitor
Strangely enough the PCB has two super-capacitors. These are 2.5V and stacked so they can handle 5V.

#### mini USB Interface
The USB interface is a Texas Instruments chip.

### EW-WU111 Wireless Unit
The `EW-WU111` is a wireless interface with `ANT` and `BLE` wireless standards. The interface can be placed in between a wireless connection cable.

### EW-SD50 Electric Wire
The `EW-SD50` is a piece of wire in various lengths with connectors at both ends. The length of the wire can be ordered between 150mm and 1600mm.

### SM-JC41 Junction Box for Di2
The junction box has four connections for cables, making it easy to insert a device to the e-Bike system.

### SM-DUE10 Speed Sensor
The `SM-DUE10` is a Reed switch with an attached cable, together with a magnet that can be attached to the spoke of a wheel. It is handy to have  the magnet around if ever you loose the magnet the e-bike doesn't function anymore.

### TL-EW02 Plug Tool (for ST-6770)
Just a piece of plastic to insert and/or remove a connector from a device.

### EC-E6000 Power Supply 42V @ 4.0A
The power supply is not just a regular power supply, but comes with a lot of electronics, including a micro-controller that talks over the power line. For the curious user you will find pictures that show the various parts of the power supply.
 
Refer to the [pictures](pictures/) directory and look for all pictures that start with the prefix `PS`.

#### micro-controller
The micro-controller on the Power Supply board is from [SinoWealth](http://www.sinowealth.com/en/softtype.asp?cat_id=32&class_id=110). It is a 8051 class processor with some standard integrated peripherals.

## Tools

There are several companies and people who offer all kinds of hacks to speed up the pedelec. Clearly that is against what is legal: a pedelec has a maximum allowed speed of 25km/h and speeding it up beyond this point is a violation. If you want speed then use an e-Bike.

### YouTube
You can find hacks on YouTube that decrease the rotation of the magnet along the sensor by a factor two. The bike electronics controller thinks it rotates slower (half the speed) and increases its support effectively towards 50km/h (in theory).

### Shimano

As already mentioned Shimano has its own support software that works with their special interface.

### eMax-tuning
Another company [emax-tuning](http://www.emax-tuning.com) provides software for the Shimano **e-Steps 8000**. They also provide some freeware that can be found [here](tools/).


