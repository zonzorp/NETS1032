# Capturing Forensics Images of Storage Devices

## Introduction
This is the second module in the NETS1032 Digital Forensics course. It is expected to be completed in week 2 of the course, with the quiz due before the start of the next class. We cover the concepts and practice of capturing forensic images of storage devices in both Windows and Linux. You are required to have root access to a Linux system and Administrator access to a Windows PC for this. It is recommended to use either [VMWare](https://vmware.com) or [VirtualBox](https://virtualbox.org) for this, but you can also use any other solution you wish for this including installing these environments on physical computers, using another virtualization solution such as Parallels, or using cloud-based virtual computers such as those sold by Amazon. It is the student's responsibility to obtain, install, and become familiar with these virtualization programs and operating environments as necessary. You are expected to be competent with the command line in both Windows and Linux.

For your lab work, ensure you have access to both a Linux desktop environment with root, and a Windows desktop with Administrator. You will be showing your work to the professor throughout the semester, so you will need to be able to share your lab system screen, and the lab system you use will need to be clearly identified as your own (you should use your own name for the login, or at least something unique to you). No marks will be given for showing work on a lab system which is not your own.


## Learning Objectives
At the end of this lesson, students will:
  * Understand the hardware, software, and process requirements for capturing images on multiple platforms
  * Recognize challenges in finding relevant forensic information
  * Understand how Disk Storage Devices and Filesystems affect evidence capture approaches
  * Be able to demonstrate the Imaging Process on Windows and Linux
  * Understand the use of Bootable Forensics Software

These objectives are in support of Learning Outcomes 2 and 5 in the Course Outline.

## To do List
   * Read through the presentation
   * Watch the videos described in the presentation
   * Watch the recorded video of the presentation found in the general chat of the Microsoft Team for this course if you did not attend the class when it was presented
   * Review the lesson materials linked below
   * Perform the learning activities as described below
   * Do the quiz found under Tests on [Blackboard](https://gc.blackboard.com) for this topic

## Lesson Material
  * [Forensic Image Capture Presentation](Presentations/NETS1032-21W-02-ForensicImageCapture.pdf)
  * See [Blackboard](https://gc.blackboard.com) for any available prerecorded video of this presentation under Weekly Learning

## Resource links in the presentation
  * [MBR](https://en.wikipedia.org/wiki/Master_boot_record)
  * [GPT](https://en.wikipedia.org/wiki/GUID_Partition_Table)
  * [NTFS](http://www.ntfs.com/ldm.htm)
  * [NTFS compared to FAT](http://www.ntfs.com/ntfs_vs_fat.htm)
  * [TrueCrypt](https://en.wikipedia.org/wiki/TrueCrypt)
  * [Cold Boot Attack](https://en.wikipedia.org/wiki/Cold_boot_attack)
  * [Forensics Linux Distros](https://distrowatch.com/search.php?category=Forensics#simple)

## Learning Activity
Watch the videos from the presentation, as well as the videos listed under additional resources. Briefly review the materials available at the other websites listed under Additional Resources.

Do the [Image Capture Assignment](Labs/Lab02-Image-Capture.md).

## Additional Resources

### Videos
* [Image Capture on Windows using FTK Imager](https://www.youtube.com/watch?v=TkG4JqUcx_U&t=1558s)
* [Image Capture on a Mac using Macquisition](https://www.youtube.com/watch?v=HJau2PkdT1o)
* [Linux Iamge Capture using Guymager](https://www.youtube.com/watch?v=FoEO9p-J15w)
* [Data Acquisition and Validation in general](https://www.youtube.com/watch?v=3JdwvXlrgyQ)

### General resources
  * [Wikipedia entry for Digital Forensics](https://en.wikipedia.org/wiki/Digital_forensics)
  * [FBI web page describing principles and standards for digital forensic activities](https://archives.fbi.gov/archives/about-us/lab/forensic-science-communications/fsc/april2000/swgde.htm)
  * [ForensicsWiki](http://forensicswiki.xyz)
  * [Comparison of file systems - Wikipedia](https://en.wikipedia.org/wiki/Comparison_of_file_systems)

### Imaging Resources
  * [Sumuri](https://sumuri.com)
  * [Veracrypt](https://veracrypt.fr)
  * [A performer Ltd, supplier of various hardware and software products for Forensic use](https://www.aperformerltd.com)
  * [ASR Data, a supplier of forensics software and hardware products](http://asrdata.com)
  * [AFF format overview and tools list](https://forensicswiki.xyz/wiki/index.php?title=AFF)
  * [AFF file format extensive detail](https://cs.harvard.edu/malan/publications/aff.pdf)
  * Tools and documentation for imaging
     * [List of Linux distros in the forensics category on distrowatch](https://distrowatch.com/search.php?category=Forensics#simple)
     * [Getting started with the SIFT workstation](https://www.youtube.com/watch?v=ai_7Fkv6igw)
     * [SIFT workstation documentation](http://sift.readthedocs.io/en/latest/)
     * [Intro to image capture in Kali](https://www.youtube.com/watch?v=QjVzLRBuR7c)
     * [Booting Kali Linux in Forensics mode](https://docs.kali.org/general-use/kali-linux-forensics-mode)
     * [dd and the dd variants for imaging storage devices](http://linuxlsga.net/dd.pdf)
     * [Accessdata FTK Imager and related tools for Windows](http://accessdata.com)
     * [OSFClone bootable USB disk imaging tools](https://www.osforensics.com/tools/create-disk-images.html)
     * [Forensic Images backgrounder](https://www.sans.org/reading-room/whitepapers/forensics/forensic-images-viewing-pleasure-35447)
     * [Live Triage Drive - USB bootable imaging tool](http://sleuthkit.org/autopsy/docs/user-docs/4.17.0/live_triage_page.html)
     * [Bulk Extractor tool](https://github.com/simsong/bulk_extractor)
  * Dealing with Encryption
     * [Bypassing self-encrypting drives](https://www.youtube.com/watch?v=dG7RQgBK0Zo)


## Graded Activity
The lab instructions tell you what parts of the lab activity are graded, and when you need to be capturing screenshots during the lab.

## Quiz
The quiz is found on Blackboard under Assignments and Tests.

## Test
There is no separate test for this topic. The quiz will count for your testing mark in this topic.

## Summary
In this module, you have been introduced to image capture.
You should now be aware of:
  * Types of data storage which can be captured
  * Methods for identifying information on storage devices
  * Tools for doing image capture and verification, both hardware and software

Completing the quiz will provide you with a measure of your knowledge in these areas. For the next class you should have your computing environment available with access to both Linux and Windows.
