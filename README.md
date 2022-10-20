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

````
sudo cfdisk y resize la particion
sudo pvresize /dev/sda3
sudo lvdisplay
sudo lvextend -l +100%FREE /dev/vg0/lv-0
sudo resize2fs /dev/mapper/vg0-lv--0
````
<br>
Run again df -h and you should now see that your volume has been extended<br>

https://packetpushers.net/ubuntu-extend-your-default-lvm-space/ <br>

## Static IP Ubuntu 22.04 ##

Locate and edit with administrative privileges the */etc/netplan/00-installer-config.yaml* file with the following configuration.
<br>

````
network:
  version: 2
  renderer: networkd
  ethernets:
    ens160:
      dhcp4: no
      addresses:
        - 10.10.9.78/24
      routes: 
      - to: default
        via: 10.10.9.1
      nameservers:
        addresses: [10.0.8.15, 10.10.9.8]
    ens192:
      dhcp4: no
````
<br>

To apply the new Netplan changes execute:
````
sudo netplan apply
````

If problems present:
````
sudo netplan --debug apply
````
<br>


