## HOW TO ATTACH ADDITIONAL EBS WITH EC2?

- STEP1: 
  Create volume from AWS EBS

- STEP2: 
  Stop the original instance & attach the volume & run below commands

- COMMANDS

List block storage & mount points
```sh
lsblk
```
Create file system (To organize file structure for external devices)
```sh
sudo mkfs -t ext4 /dev/xvdf1
# (Here 'xvdf1' is the name of volume, replace it with actual volume name xvdb1, xvdc1, etc from lsblk command)
```
Create any directory to mount the volume
```sh
sudo mkdir /disk2
```                                            
Create mount point
```sh
sudo mount /dev/xvdf1 /disk2                                  
```
Verify mount
```sh
lsblk
```
Unmount original volume (optional)
```sh
sudo umount /disk2                                                       # 
```
