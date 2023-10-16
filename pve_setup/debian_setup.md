# Add repo for non-production packages in /etc/apt/sources.list
deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription

# Remove enterprise repos in /etc/apt/sources.list.d/ceph.list
# Remove enterprise repos in /etc/apt/sources.list.d/pve-enterprise.list

# Update the system
`apt update && apt dist-upgrade -y`

# Install basic packages
`apt install -y vim net-tools`

# Reboot

# Edit GRUB to be able PCI-Passthrough
Edit /etc/default/grub line to look like this (AMD):
`GRUB_CMDLINE_LINUX_DEFAULT="quiet amd_iommu=on"`\
`update-grub`
# Add kernel modules
Edit /etc/modules with these lines:
`vfio
vfio_iommu_type1
vfio_pci
vfio_virqfd`
`reboot`


