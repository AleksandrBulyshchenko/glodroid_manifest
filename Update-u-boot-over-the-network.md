First you need to configure tftp:

https://pingvinus.ru/note/tftpd-server-client-ubuntu-linux

Using serial console stop u-boot execution and enter the commands below:
```
dhcp ${kernel_addr_r} 172.28.184.24:u-boot-sunxi-with-spl.bin && mmc dev 0 && mmc write ${kernel_addr_r} 0x10 0x400
# 0x400-size in 512b blocks
```
