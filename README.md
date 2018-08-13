# Shimano e-Steps
This repository is dedicated to the Shimano e-Steps as I happen to have an e-Bike that is fitted with the Shimano drive-train. There is hardly any technical information on the electronics, so I decided to do a little exploring myself. 

## e-Bikes
Electrification of a bike is very populair. There are two basic bike types:

- pedelec, limited to 25km/h, no helmet required
- speed e-bike, limited to 45km/h, requires a helmet, insurance

Among the pedelecs, drive-trains of Bosch, Shimano, Bafang and Yamaha are used as well as automatic transmission systems of Shimano, NuVinci, etc. which make riding a bike a joy.


## Documents
You can find some patents in the [patents](patents/) directory.

## Communication
The communication between the different system parts on the e-bike use power line communication (i.e. data is superimposed on the DC voltage).

**`TODO`**<br>

- Hookup oscillocope and see what happens
- Measure voltages on the "bus"


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


## Accessoires

### SM-PCE1 PC Linkage Device
The `SM-PCE1` is an USB interface to connect the e-Steps system to a PC. It is used for service, configuration and maintenance. It is normally not required for a bike owner to have such an interface, but my curiosity was triggered to find out if I can hookup Bluetooth to my bike.

- [BOX](https://user-images.githubusercontent.com/1014001/43896685-f58adc2a-9bd9-11e8-9821-9a8bd3c760c1.jpg)
- [PCB TOP](https://user-images.githubusercontent.com/1014001/43896881-a103f028-9bda-11e8-8a23-826b529461cf.jpg)
- [PCB BOTTOM](https://user-images.githubusercontent.com/1014001/43896903-ae41b82e-9bda-11e8-99b4-9aa84fdd4943.jpg)
- [BOX INNER SIDE TOP](https://user-images.githubusercontent.com/1014001/43896922-be125c4a-9bda-11e8-8097-daa525b39b0f.jpg)
- [BOX INNER SIDE BOTTOM](https://user-images.githubusercontent.com/1014001/43896908-b4724cd6-9bda-11e8-948c-682df6467245.jpg)
- [BOX BACK SIDE](https://user-images.githubusercontent.com/1014001/43896913-b80eea16-9bda-11e8-8450-f36e1a5e1dfe.jpg)
- [BOX SIDE VIEW](https://user-images.githubusercontent.com/1014001/43897124-60b91e7a-9bdb-11e8-816b-77eb42061afe.jpg)

#### Super Capacitor
Strangely enough the PCB has two super-capacitors. These are 2.5V and stacked so they can handle 5V.

#### mini USB Interface
The USB interface is a Texas Instruments chip, 


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
