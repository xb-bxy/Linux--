# Linux系统移植

## Linux-uboot烧录
- tftp 0x48000000 ubootpak.bin (用tftp将文件下载到48000000起始位置上)
- update_mmc 2 2ndboot 0x48000000 0x200 [ubootpak.bin的长度] (是将下载到内存中的uboot烧写到emmc中)
- 重启板子

## 
