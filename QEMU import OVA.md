# Import OVA and convert to QCOW2

## 1. Extract OVA to get VMDK files

````
tar xvf <ova-file-name>
````

## 2. Convert VMDK to QCOW2 for each disk using qemu-img

````
qemu-img convert -O qcow2 <source-disk.vmdk> <destination-disk.qcow2>
````
