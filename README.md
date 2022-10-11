# Cheat-Sheet-Linux
Comandos Utiles

## Expand LVM ###
Edit the virtual machine and “Expand” the desired Volume<br>
Reboot the virtual machine<br>
SSH into the virtual machine<br>
Run sudo lvdisplay to get the name of the logical volume<br>
Run sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv to extend the volume to the maximum size available<br>
Run df -h to see the status of the filesystem free space<br>
Grab the name of your target filesystem (typically /dev/mapper/ubuntu--vg-ubuntu--lv)<br>
Run sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv to resize the filesystem<br>
Run again df -h and you should now see that your volume has been extended<br>

https://packetpushers.net/ubuntu-extend-your-default-lvm-space/ <br>

## Static IP Ubuntu 22.04 ##

```
network:
    ethernets:
        enp0s3:
            dhcp4: false
            addresses: [192.168.1.202/24]
            gateway4: 192.168.1.1
            nameservers:
              addresses: [8.8.8.8,8.8.4.4,192.168.1.1]
    version: 2
```
<br>
