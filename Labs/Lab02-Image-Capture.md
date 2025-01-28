# Forensic Image Capture Lab
In this lab, we will try capturing forensic images of filesystems using various tools. In order to keep the size of the images and time required for the task to a minimum, we will create a small drive specifically for this purpose. In order to use tools for both Windows and Linux, we will create filesystems which are Windows-compatible. We will conveniently ignore the main Windows drive because it is too big. While searching a real drive is a valuable exercise, it is also very time consuming.

## The incident
The scenario we will emulate is one where Donald has downloaded some files from the internet to his work computer. Donald then became concerned that he shouldn't have those files on the work computer, and deleted some of them. But most of the people in the office saw him do this (he does things like this all the time) and several reported to their manager that he was using his computer for inappropriate activities, because the company does sensitive military work and there are strict policies about how computers get used. It is well known amongst the group of co-workers that Donald is a Clint Eastwood fan and regularly uses his work computer to find photos of him on company time. We have been instructed by our manager Robert to examine Donald's disk to see if the allegations made by his co-workers are true. It is policy in our company that anything kept on work equipment is the property of the company and no expectation of privacy is warranted. Robert has the authority to have Donald's computer searched.

## Manufacture the incident scene
First we will have to commit Donald's misconduct. We will make a small second drive to put the files on to make the imaging tasks faster and more focused. We will download the files, then delete them and remove the drive.

### Windows
1. Create a Windows 10 VM, or re-use an existing windows VM
   1. Add a second hard disk to your VM, 100MB in size is enough, pre-allocate space, don't split files, and boot your VM
   1. Go to Disk Management in Windows
   1. Initialize the tiny drive if necessary, you will have to use MBR for the partition table
   1. Create a new simple volume on the second hard disk of type FAT32 using half the disk
   1. Create another new simple volume on the second hard disk of type NTFS using the remainder of the disk
   1. Assign drive letters to both
   1. Format both new logical drives, make sure you use FAT for one, and NTFS for the other
   1. Download https://zonzorp.net/pics.zip and extract the files in it to your Downloads folder
   1. Go to Windows Explorer and navigate to the new FAT drive
      1. Copy the files unpacked from the pics.zip archive onto the new FAT drive
      1. Delete the whoisit folder and its files from the new FAT drive
      1. Repeat this process on the new NTFS drive
   1. Go back to the disk management tool and remove the drive letters from the FAT and NTFS partitions of your tiny drive
1. Shut down your Windows VM, *not sleep, suspend, or hibernate*
1. Go to your Windows VM settings while it is shut down and select the tiny drive, then click to Remove Disk, *do not trash the file, keep it*
#### Your tiny drive is now an orphan, disconnected from the Windows VM

## Investigation Preparation
The first step in the investigation is to get authorization and the definition of the investigation including its scope.
The next step is to identify what evidence we will examine.
The next step is to gather the evidence, i.e. make an image of the drive.
As we perform these tasks, we need to document our activities so that our results are credible and usable.
Your final report should document your work on this investigation, what you did, when you did it, and who else may have been involved in your doing it. Create a directory to hold all the files related to this investigation and start a document file to record a list of your activities. Add entries describing the purpose of the investigation, the evidence items identified, and the authorization obtained to access the evidence items.
```bash
mkdir -p ~/Documents/Donald-investigation
cd ~/Documents/Donald-investigation
vi activities.txt
```

## Begin examining the evidence
Now we will take the role of investigator. First we will create or appropriate a forensics computer. Then we will attach the suspect drive to our forensics system, and image the evidence drive in multiple ways.

### Linux
1. Create a Linux desktop VM with the imaging tool
   * For this lab, you only need to install Ubuntu desktop, or use an existing Ubuntu VM like the one from our NETS1028 class and install dc3dd and gzip
```bash
apt update
apt install dc3dd gzip
```
1. Attach the tiny second drive to the forensic station.
   * Shutdown the Linux machine because VMWare insists on it to add a drive
   * Choose to Add an existing drive in the VM settings
      * Navigate to where the tiny drive is saved under the Windows VM folder
      * take the drive from the other VM in VMWare when attaching the existing hard disk as a second drive
1. Determine the drive logical name to use for examining the drive.
   * The lshw command can identify hardware even if it is not in use
```bash
sudo lshw -class disk -businfo
```
   * It will be easy enough to see which disk in the output is the 100MB disk, and get its logical name, probably **/dev/sdb**
1. Use fdisk to view the partition table of the suspect drive
```bash
sudo fdisk -l /dev/sdb
```
   * note the partition types
   * note the total size of the tiny drive
   * how does that compare with the sum of sizes of the partitions on it? the size reported by lshw? the size reported by df?
   * does the second partition start where the first ended, or is there a gap? Is there unallocated space at the end of the 2nd partition?
1. Use dd on your tiny drive to capture each partition, and to capture the entire drive
   * use gzip to compress the resulting file to save space
   * use sudo to get root privileges for reading the raw drives
   * use shell redirects so that the output file is not owned by root
```bash
sudo dd if=/dev/sdb bs=1M  | gzip > wholedrive.dd.gz
sudo dd if=/dev/sdb1 bs=1M | gzip >part1.dd.gz
sudo dd if=/dev/sdb2 bs=1M | gzip >part2.dd.gz
```
1. Use dc3dd to retrieve an image of the whole drive and compare it to the one you got with dd
   * use dc3dd to create an image file from the source drive
   * gzip the resulting file to save space
   * use shell redirects to avoid unintentional root file ownership
   * specify multiple hashes to be generated and saved to a hash log
```bash
sudo apt update
sudo apt install dc3dd
sudo dc3dd if=/dev/sdb hash=md5 hash=sha1 hash=sha256 hash=sha512 hlog=wholedrive.hlog | gzip > wholedrive.dc3dd.gz
```
1. Compare the two files using the cmp command
   * uncompress the files
   * cmp the expanded files, are they the same?
   * use gzip to recompress the files
```bash
gunzip wholedrive.dd.gz wholedrive.dc3dd.gz
cmp wholedrive.dd wholedrive.dc3dd
gzip wholedrive.dd wholedrive.dc3dd
```
   * what do you get for a result if you just **cmp** the 2 gzipped files?
1. Generate an md5 hash and some SHA hashes for the wholedrive image file created by dd, and compare them
```bash
gunzip < wholedrive.dd.gz|md5sum > wholedrive.md5
gunzip < wholedrive.dd.gz|sha1sum > wholedrive.sha1
gunzip < wholedrive.dd.gz|sha256sum > wholedrive.sha256
gunzip < wholedrive.dd.gz|sha512sum > wholedrive.sha512
more wholedrive.md5 wholedrive.sha*
```
   * which one generates the largest hash value (meaning fewer collisions or probability for false matches)?
   * which one has the shortest signature (meaning the most collisions or probability for false matches)?
   * are the hashes identical to the ones in the dc3dd hash log file?

1. Add notes to your report document detailing the image files you captured, and their hashes.

## Create a snapshot
Use the following command to properly shutdown your ubuntu VM.

```bash
sudo poweroff
```

When the VM has finished shutting down, use your file manager to find the files for your VM, which typically will be in a directory called `Virtual Machines` in your home directory. Open the file for your vm called VMNAME.vmx and add the following line to the end of the file.
```bash
disk.EnableUUID = "TRUE"
```

Now use the VM or Virtual Machine menu in VMWare to create a snapshot. You should create a snapshot after every lab is completed, so that if you mess something up, the worst impact is that you will have to go back to your snapshot and redo the current lab. If you don't have the snapshots, you will have to start back at lab 0 if you mess up your VM during the semester. Once you have made the snapshot, you can run the VM again in VMWare so that it is ready for use in the next lab.

## Grading
This lab is preparation for the filesystem analysis lab. This lab is not marked, but the files produced will be required for the filesystem lab.
