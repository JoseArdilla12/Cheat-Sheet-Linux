# Cheat-Sheet-Linux
Comandos Utiles

## Expand LVM ###
Edit the virtual machine and go under “Hard Drive”
Click on “Edit”, select “Expand” and enter the desired size
Reboot the virtual machine
SSH into the virtual machine
Run sudo lvdisplay to get the name of the logical volume
Run sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv to extend the volume to the maximum size available
Run df -h to see the status of the filesystem free space
Grab the name of your target filesystem (typically /dev/mapper/ubuntu--vg-ubuntu--lv)
Run sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv to resize the filesystem
Run again df -h and you should now see that your volume has been extended
