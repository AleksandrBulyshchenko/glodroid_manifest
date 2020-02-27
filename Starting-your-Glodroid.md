First of all, currently this project only supports Orange Pi 2 PlusE, so if you don't want to put extra effort into adding support for other platform then please choose Pi 2 PlusE. Adding support for other platform should be covered in other document.

We strongly advice you to mount some cooling system to your Orange Pi since Android requires relatively much of resources to run and overheats without ventilators or radiator will occur. Cooling is **necessary** for stable and long-term work of Android on Orange Pi.

Next, you need *some device* (I will clarify later how it's called) to connect to Orange via serial port. It is needed for working with bootloader and kernel consoles. In theory you could skip this part if you don't need to work with bootloader/kernel, but it is *very* unlikely. It connects to pins on the pic below:

*Sorry, I'll put pic a bit later*

Then you need to have sd-card. 2 GB would be enough. After building android you could find out/target/product/sdcard.img file. Use it to flash sd-card, with dd or some better tool.

Put sd-card in respective port, connect Orange Pi to power, connect your working machine and Orange via usb to work via adb later. Turn your board on. Enjoy launch of Android (or failure to do so).