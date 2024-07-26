## IMPLEMENTING WORDPRESS WEBSITE WITH LOGIC VOLUME MANAGEMENT (LVM) STORAGE MANAGEMENT 

To inspect what block device is attched to the server
lsblk

![21](./wops_21.png)


![5](./wops_5.png)
To see all mount and free space on the web-server
df -h
To create a single partition on each of the disk using the gdisk Utility, run the below command:
sudo gdisk /dev/nvme1n1
sudo gdisk /dev/nvme2n1
sudo gdisk /dev/nvme3n1

![33](./wops_33.png)

To create a single partition on each of the disk using the gdisk Utility, run the below command:
sudo gdisk /dev/nvme1n1
sudo gdisk /dev/nvme2n1
sudo gdisk /dev/nvme3n1

![5](./wops_5.png)

To view the newly configured partition on each of the 3 disks
lsblk 

![17](./wops_17.png)

Install lvm2 package using the below command;
sudo yum install lvm2

![13](./wops_13.png) 

Run the below command to check for available partitions

sudo lvmdiskscan

![34](./wops_34.png)

To format the logical app and log Volumes with ext4 file system using mkfs.ext4
sudo mkfs -t ext4 /dev/webdata-vg/apps-lv
sudo mkfs -t ext4 /dev/webdata-vg/logs-lv

![27](./wops_27.png)

To back up files in the log directory /var/log into home/recovery/logs using the rsync utility script, please run the below;
sudo rsync -av /var/log/. /home/recovery/logs/

![25](./wops_25.png)

To update /etc/fstab so that the mount configuration will persist after restart. Copy the UUID of the device to upate the /etc/fstab
sudo blkid

![24](./wops_24.png)

To test the configuration and reload the Daemon
sudo mount -a 
AND

sudo systemctl daemon-reload

![23](./wops_23.png)

HEADING - INSTALLING WORDPRESS AND CONFIGURING IT TO USE MYSQL DATABASE


Connect to the DB-Server via ssh. Then, to see the newly created devices

lsblk

![21](./wops_21.png)

To create a single partition on each of the 3 disks

sudo gdisk /dev/nvme1n1
sudo gdisk /dev/nvme2n1
sudo gdisk /dev/nvme3n1

![20](./wops_20.png)


![19](./wops_19.png)
![18](./wops_18.png)
![17](./wops_17.png)
![16](./wops_16.png)
![15](./wops_15.png)
![14](./wops_14.png)
![13](./wops_13.png)
![11](./wops_11.png)
![9](./wops_9.png)
![8](./wops_8.png)
![7](./wops_7.png)
![5](./wops_5.png)
![4](./wops_4.png)




