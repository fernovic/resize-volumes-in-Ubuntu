# resize-volumes-in-Ubuntu
```bash
pvresize /dev/sda3
lvresize -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv
```
you're working with LVM (Logical Volume Manager) to resize volumes in Ubuntu. Let's break down each command:

1. `pvresize /dev/sda3`: This command is used to resize physical volumes. It adjusts the size of the physical volume on the disk. `/dev/sda3` is the device representing the physical volume you want to resize.

2. `lvresize -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv`: This command is used to resize logical volumes. It increases the size of the logical volume `/dev/mapper/ubuntu--vg-ubuntu--lv` by adding all available free space (`+100%FREE`). 

3. `resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv`: This command is used to resize the filesystem on the specified logical volume (`/dev/mapper/ubuntu--vg-ubuntu--lv`). It adjusts the filesystem to occupy all available space after resizing the logical volume.

Make sure to double-check the commands and ensure that you have backups in place before performing any resizing operations, as they can potentially result in data loss if not done correctly.

# testing

```bash
df -h
```

The df -h command is used to display disk space usage in a human-readable format. Here's what each column in the output represents:

    Filesystem: The device or filesystem name.
    Size: Total size of the filesystem.
    Used: Amount of space used on the filesystem.
    Available: Available space on the filesystem.
    Use%: Percentage of space used.
    Mounted on: The directory where the filesystem is mounted.

Running this command will provide you with a summary of disk space usage across all mounted filesystems on your system.
