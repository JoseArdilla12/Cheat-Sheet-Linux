# Sleep fix Ryzen

grub default config
```
/etc/default/grub

add amd_iommu=off 
GRUB_CMDLINE_LINUX_DEFAULT="quiet amd_iommu=off"
```
