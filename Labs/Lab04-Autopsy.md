# Linux/MacOS Image Analysis with Autopsy

In this lab, you will capture a forensic image of a Linux filesystem and analyze it using the Autopsy web interface to the sleuthkit tools. In order to keep the size of the image and time required for the task to a minimum, we will create a small filesystem specifically for this purpose.

## Create filesystems to capture on virtual disk under Linux

### Create a small filesystem on a tiny drive that we can use for our forensic image
   1. On your Linux VM
   1. Shutdown your Linux client OS
   1. Add a hard disk to your VM, 100MB in size is enough
   1. Boot your VM
   1. Start a terminal window
   1. In your terminal window, identify the drive name using the fdisk or lsblk command (_i.e. look for the 100MB drive_)
      ```
      sudo fdisk -l
      sudo lsblk
      ```
   1. Use fdisk or a similar tool to put a single partition on the drive, *be very careful you use the right drive name*
      ```
      sudo fdisk /dev/sdb
      ```
      * at the fdisk prompt, enter *n* to make a new partition and just take the defaults for all questions it asks so that you get a single partition that includes the entire drive
      * when you get the fdisk prompt again, enter *w* to write the partition table to the disk
   1. Make a typical Linux filesystem in the partition
      ```
      sudo mkfs -t ext4 /dev/sdb1
      ```
   1. Make a directory to attach the new drive to
      ```
      sudo mkdir /m
      ```
   1. Mount the new drive so you can access the files on it
      ```
      sudo mount -t ext4 /dev/sdb1 /m
      ```
   1. On the new drive, create some files, then delete some files, so you will have the opportunity to compare the results of deleting files in Linux versus Windows
      ```
      sudo bash << EOF
      cd /m
      wget zonzorp.net/pics.zip
      unzip pics.zip
      mv pics.zip /root
      rm -rf catfiles
      EOF
      ```
   1. Detach the new drive so it can be imaged
      ```
      sudo umount /m
      ```
   1. Create an image file from the new drive, install dc3dd first if necessary *be very careful you use the right drive name*
      ```
      sudo apt update
      sudo apt install dc3dd
      sudo dc3dd if=/dev/sdb hash=md5 hash=sha1 hash=sha256 hash=sha512 hlog=linuxdrive.hlog | gzip > linuxdrive.dc3dd.gz
      ```

## Run Autopsy Linux image analysis tool
   1. Copy your image file and hash files to your Forensics station (where you installed the Autopsy tool)
   1. Open a new case and add a host for the suspect machine under investigation
   1. Add an image file data source, using the image file we just captured named linuxdrive.dd
   1. For image file import, put in your hash values from the linuxdrive.hlog file
   1. This is our only image file, so just click Ok when it is done
   1. Return to the Filesystem list, and Explore the Analyze function, as well as the timeline function

## Grading
This lab is not marked. It is a learning activity to gain familiarity with doing storage device imaging.
