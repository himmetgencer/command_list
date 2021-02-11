# Linux Commands

summarize disk usage
```sh
du -h folder_name
du -h *
sudo find / -xdev -type f -size +100M
```

summarize free disk space
```sh
df -h
sudo du -s -k /*
du -sm * | awk '$1 > 10'
```

```sh
mkfs.fat device_link -I
```

View All Disk Partitions
```sh
fdisk -l
```

Install VirtualBox Guest Additions in Ubuntu
```sh
sudo apt install build-essential dkms linux-headers-$(uname -r)
```

Access shared folder in virtualbox
```sh
sudo adduser [your-user-name] vboxsf
```

scp copy directory
```sh
scp -r username@ip:remoteDir destinationDir
```

diagnostic message
```sh
sudo dmesg -T
```

for writing to NTFS partitions
```sh
sudo apt-get install ntfs-3g
```


| Description | Link |
| ------ | ------ |
| - | -|
