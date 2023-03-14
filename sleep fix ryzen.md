#AMD Sleep fix

grub default config
```
/etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet amd_iommu=off"
```
