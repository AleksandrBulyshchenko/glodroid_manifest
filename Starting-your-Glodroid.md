### Supported platforms
First of all, currently this project only supports Orange Pi 2 PlusE, so if you don't want to put extra effort into adding support for other platform then please choose Pi 2 PlusE. Porting other Orange Pi models is a doable thing, though adding support for other platform should be covered in other document.

### Additional equipment
We strongly advice you to mount some cooling system like heatsink or fan. to your Orange Pi since Android requires relatively much of resources to run and overheats without fans or heatsinks will occur. Cooling is **necessary** for stable and long-term work of Android on Orange Pi.

Another piece of equipment necessary for work is obviously, power adapter. We suggest to have one that has 3-4A, since Android is a bit of resource-intensive OS.

Please note that Android **requires** display for work. It simply won't lauch without it. Orange Pi has an HDMI connector to connect display.

Next, you need USB-to-TTL converter to connect to Orange via serial port. It is needed for working with bootloader and kernel consoles via tool called `minicom`. Each Orange Pi board has TTL UART, though it's location could vary. It has 3 pins: GND, Rx and Tx. Converter connects to Orange in the following principle: GND to GND, Rx to Tx, Tx to Rx. Exact position of each pin could vary between Orange models, so please consult with documentation. For example, here's how Orange Pi Win is connected:

![Pins on Orange](https://i.imgur.com/04QH2uE.png) ![Pins on converter](https://i.imgur.com/BtyhB8X.png)

White wire is GND, purple one connects Rx to Tx, grey one connects Tx to Rx.

### Making bootable image of Android
Orange Pi launches OS from sd-card, therefore you should build image and write it on one. sd-card with 2 GB storage would be enough, since now Android image takes like 1,2 GB. To build Android execute those commands inside of Android directory:
```bash
source ./build/envsetup.sh
lunch plus2e-userdebug
make sdcard
```

After building Android you could find out/target/product/sdcard.img file. Use it to flash sd-card with dd or some better tool, for example:
```bash
cd ${ANDROID_ROOT}/
export card=/dev/sdX
dd if=out/target/product/plus2e/sdcard.img of=${card} bs=4k count=300000
sync
```

Put sd-card in respective port, connect Orange Pi to power, connect your working machine and Orange via usb to work via adb later. Execute `minicom -D /dev/ttyUSB0` to see bootloader logs from board. Turn your board on. Enjoy launch of Android (or failure to do so).

### Things to do after launch:
- Build and run VTS tests (_link on how-to-run-vts to be provided_).
- Check the Roadmap on features to work on (_link to be provided_).
- Check the [issues](https://github.com/glodroid/glodroid_manifest/issues) and try to resolve them.