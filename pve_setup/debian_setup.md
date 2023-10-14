# Add repo for non-production packages in /etc/apt/sources.list
deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription

# Remove enterprise repos in /etc/apt/sources.list.d/ceph.list
# Remove enterprise repos in /etc/apt/sources.list.d/pve-enterprise.list

# Update the system
`apt update && apt dist-upgrade -y`