# docker
docker learning
安装双系统的时候，先装win7再装centos的时候，需要修改grub2的配置i
1 1.sudo vi /boot/grub2/grub.cfg
2 2.找到 ### BEGIN /etc/grub.d/30_os-prober ###
3    在后面添加
4    menuentry "Windows 7 (loader) (on /dev/sda1)" {
5      insmod ntfs
6      set root=(hd0,1) #由于我的windows安装在硬盘的C盘，故（hd0,1)
7      chainloader +1
8    }
