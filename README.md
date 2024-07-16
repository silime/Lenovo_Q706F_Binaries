# UEFI firmware dumped from XBL/UEFI image.



## Tool



[UEFIReader](https://github.com/WOA-Project/UEFIReader) by [Gustave Monce](https://github.com/gus33000)

## Use



- UEFI needed.
- You may need to refer uefiplat.cfg to get some useful information.
- You may want panel cfg and fill it into dsdt. ...

## Notice



- Some binaries(e.g. ButtonDxe.efi/UsbConfigDxe.efi) extracted here were patched by us.
- If you want the original, you can extracted these binaries from the xbl images we provided.
- We won't provide IDA files anymore.

## List



------

### SM8250



| Device Name                 | CodeName |
| --------------------------- | -------- |
| Lenovo Xiaoxin Pad Pro 12.6 | TB-Q706F |

### Mainline HW status

|           Component           |                           Model                           |            Status             |                            Notes                             |
| :---------------------------: | :-------------------------------------------------------: | :---------------------------: | :----------------------------------------------------------: |
|              SoC              |             Qualcomm SM8250-AC Snapdragon 870             |               Y               |                                                              |
|              UFS              |                  Kioxia THGJFAT0T44BAILB                  |               Y               |                                                              |
|            SD card            |                             -                             |               Y               |                                                              |
|            Display            |                    samsung AMSA26ZP01                     |               P               | Dual DSI samsung 2k dsc 2560 x 1600 120Hz 12.6" AMOLED <br />The backlight does not work |
|          Touchscreen          |                  Goodix GT9966/GT6975P ?                  |               Y               |               Goodix berlin series spi@a94000                |
|           Pen input           |                             N                             | Compatible with MPP 1.51 pens |                                                              |
|           Touchpad            | hid-over-i2c (Available through detachable keyboard only) |               N               |                  addr: 0x60, bus: 0xa84000                   |
|           Keyboard            |                       hid-over-i2c                        |               N               |                i2c Address 0x61,bus:0x98c000                 |
|             Audio             |                      Cirrus CS35L41                       |               N               |     bus: 0x994000， 4x Speaker Amp, one for each speaker     |
|      Everest-Semi ES7210      |                      For microphone                       |                               |                  addr: 0x40, bus: 0x994000                   |
|       synaptics as33970       |                     For microphone ?                      |                               |                   addr: 0x41,bus:0x994000                    |
|         Pen Charging          |                        NXP CTN730                         |                               |                  addr: 0x28, bus: 0x984000                   |
|           Charging            |                    Qualcomm SMB1390 ?                     |               N               |        addr: 0x10, bus: 0x884000 Driver lenovo_jeita         |
|            Buttons            |                           GPIO                            |               Y               |                                                              |
|             USB-C             |                     USB 3.0 & USB 2.0                     |               Y               |                                                              |
|        Role switching         |                             N                             |                               |                                                              |
| onsemi NB7VPQ904M DP redriver |                             N                             |                               |                  addr: 0x19, bus: 0x990000                   |
|            FSA4480            |                             N                             |                               |                  addr: 0x43, bus: 0x990000                   |
|           VBUS out            |                             N                             |                               |                                                              |
|          Fuel gauge           |                 Texas Instruments bq27541                 |               Y               |                  addr: 0x55, bus: 0x884000                   |
|     Ambient light sensor      |                      Lite-On LTR-308                      |               N               |                         FastRPC-SDSP                         |
|     Time-of-flight sensor     |            AMS (Austria Mikro Systeme) TMF8801            |               N               |                         FastRPC-SDSP                         |
|         Magnetometer          |                        AKM ak0991x                        |               N               |                         FastRPC-SDSP                         |
|             Wi-Fi             |                     Qualcomm QCA6390                      |               N               | lspci didn't find any devices, maybe the regulator was misconfigured |
|          Fingerprint          |                          Goodix                           |               N               |                                                              |



### i2c Table

Android messes up the i2c numbering. This is the real i2c numbering corresponding to mainline, showing only those that have devices attached.

| Real  | Android | Address  |
| :---: | :-----: | :------: |
| i2c1  |  i2c0   | 0x984000 |
| i2c3  |  i2c6   | 0x98c000 |
| i2c4  |  i2c2   | 0x990000 |
| i2c5  |  i2c3   | 0x994000 |
| i2c9  |  i2c4   | 0xa84000 |
| i2c13 |  i2c7   | 0xa94000 |
| i2c15 |  i2c5   | 0x884000 |



