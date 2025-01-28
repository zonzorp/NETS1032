# Working with Linux Filesystem Images

## Introduction
This lesson provides some conceptual and practical information on processes, tools, and considerations for working with captured images of Linux Filesystems.

For your lab work, ensure you have access to both a Linux desktop environment with root, and a Windows desktop with Administrator. You will be showing your work to the professor throughout the semester, so you will need to be able to share your lab system screen, and the lab system you use will need to be clearly identified as your own (you should use your own name for the login, or at least something unique to you). No marks will be given for showing work on a lab system which is not your own.


## Learning Objectives
At the end of this lesson, students will:
   * Understand what Linux Filesystem Images Contain, including metadata
   * Begin to explore the kinds of artifacts that might be of interest in Linux Filesystem Images
   * Begin using tools for Analyzing Linux Filesystem Images
   * Demonstrate using Linux forensic analysis tools to work with metadata and deleted files in Linux Filesystem Images

These objectives are in support of Learning Outcomes 2, 3, 4, and 6 in the Course Outline.

## To do List
   * Read through the presentation
   * Watch the videos described in the presentation
   * Watch the recorded video of the presentation found in the general chat of the Microsoft Team for this course if you did not attend the class when it was presented
   * Review the lesson materials linked below
   * Perform the learning activities as described below
   * Do the quiz found under Tests on [Blackboard](https://gc.blackboard.com) for this topic

## Lesson Material
   * [Working with Linux Filesystems Presentation in PDF format](Presentations/NETS1032-21W-04-LinuxFilesystemImages.pdf)
  * See [Blackboard](https://gc.blackboard.com) for any available prerecorded video of this presentation under Weekly Learning
   * Links from the presentation
      * [Example of using Linux Forensic Tools](https://opensource.com/article/18/4/linux-filesystem-forensics)
      * [RAM and file slack contents discussion](https://superuser.com/questions/1058565/file-slack-ram-slack-why-does-windows-write-arbitrary-ram-bytes-to-disk-does)

## Learning Activity
Watch the videos from the presentation, as well as the videos listed under additional resources. Briefly review the materials available at the other websites listed under Additional Resources.
Do the [Linux Filesystem Analysis Assignment](Labs/Lab04-Autopsy.html)

## Additional Resources    

### Videos
   * [Linux filesystems forensic activities demonstrated using the SIFT workstation, long and covers many specific exampless of metadata and expected filesystem contents](https://www.youtube.com/watch?v=HTEj8UY2TA8)
   * [Very low level detailed talk describing recovering data from destroyed EXT4 filesystems](https://www.youtube.com/watch?v=6pzm6909IvY)

### Software Tools for Linux filesystems forensic analysis
   * [Autopsy/Sleuthkit](http://sleuthkit.org/index.php)
   * [Belkasoft Evidence Center](https://www.youtube.com/watch?v=mu2mYMOVzyQ)
   * [GFI's list of forensic tools](https://techtalk.gfi.com/top-20-free-digital-forensic-investigation-tools-for-sysadmins)
   * [Sleuthkit Wiki](https://wiki.sleuthkit.org)
   * [Command line tools for Linux including ils, mactime, fls, istat, icat](http://wiki.sleuthkit.org/index.php?title=TSK_Tool_Overview)
   * [Infosec Institute Forensic Tools list](http://resources.infosecinstitute.com/computer-forensics-tools/)
   * [Forensics Wiki Tools list](https://forensicswiki.xyz)
   * [Adding hash databases to Autopsy](http://www.sleuthkit.org/autopsy/help/hash_db.html)
   * [Current NIST RDS hash databases](https://www.nist.gov/itl/ssd/software-quality-group/national-software-reference-library-nsrl/nsrl-download/current-rds)
   * [Recovering different kinds of partitions, filesystems, and files using Linux](https://likegeeks.com/recover-deleted-files-on-linux)
   * [How to access Linux filesystems using WSL2 on Windows for some virtual disks](https://www.bleepingcomputer.com/news/microsoft/windows-10-now-lets-you-mount-linux-ext4-filesystems-in-wsl-2/)
    * [Linux LVM – Volume Creation & Operations](https://www.unixarena.com/2013/08/linux-lvm-volume-creation-operation.html/)

### General resources
   * [Digital Forensics Tool Testing image investigations examples](http://dftt.sourceforge.net)
   * [Breach detection with Linux filesystem forensics](https://opensource.com/article/18/4/linux-filesystem-forensics)
   * [Data Hiding in Slack Space Revisited](https://www.semanticscholar.org/paper/Data-Hiding-in-Slack-Space-Revisited-Mohan-Thampy/8d29f53300b7df66cdd82442300c3c4a57f0833c)
   * [Cross mount point examples](http://systemmanager.ru/nbadmin.en/ch29s12s12s03.htm)

### Standards references, a starting point
   * [The File System Hierarchy Standard visualized or: "What are the directories in / for?"](https://www.reddit.com/r/linux/comments/8kt99k/the_file_system_hierarchy_standard_visualized_or/)

## Graded Activity
The lab instructions tell you what parts of the lab activity are graded, and when you need to be capturing screenshots during the lab.

## Quiz

The quiz is found on Blackboard under Assignments and Tests.

## Test

There is no separate test for this topic. The quiz will count for your testing mark in this topic.

## Summary
In this module, you have been introduced to working with Linux filesystems images.
You should now be:
* Aware of the uses and limitations of selected forensic tools for investigating Linux Filesystem Images
* Familiar with the kinds of evidence that can be found in a Linux filesystem
* Capable of selecting tools for working with Linux filesystems images, both hardware and software

Completing the quiz will provide you with a measure of your knowledge in these areas. For the next class you should have your computing environment available with access to both Linux and Windows.

