# Linux系统移植
## 给emmc重新分区
- fdisk 2 3 0x100000:0x4000000 0x4100000:0x2f200000 0x33300000:0
> 给第2个emmc设备分成3个区:
>                 第一区从0x100000字节（1MB）开始分配0x4000000个字节（64MB）        Linux内核区
>                 第二区从0x4100000字节（65MB）开始分配0x2f200000个字节（764MB）    rootfs文件系统区
>                 第三区从0x33300000字节（819MB）开始分配0剩余所有字节（剩余全部分配）appfs应用程序区

## uboot烧录
- tftp 0x48000000 ubootpak.bin (用tftp将文件下载到48000000起始位置上)
- update_mmc 2 2ndboot 0x48000000 0x200 [ubootpak.bin的长度] (是将下载到内存中的uboot烧写到emmc中)
- 重启板子

## uImage烧录 (Linux内核)
- 
