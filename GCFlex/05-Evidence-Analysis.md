# Evidence Analysis

## Introduction
This lesson provides some conceptual and practical information on processes, tools, and considerations for analyzing evidence obtained from Filesystem or Storage Device Images.

For your lab work, ensure you have access to both a Linux desktop environment with root, and a Windows desktop with Administrator. You will be showing your work to the professor throughout the semester, so you will need to be able to share your lab system screen, and the lab system you use will need to be clearly identified as your own (you should use your own name for the login, or at least something unique to you). No marks will be given for showing work on a lab system which is not your own.


## Learning Objectives
At the end of this lesson, students will:
   * Have performed a directed investigation of a possible crime scene
   * Have demonstrated using forensic analysis tools to extract evidence from a specific image of a wiped removable drive
   * Have demonstrated the ability to produce a forensic report using a standard report format provided in the course materials

These objectives are in support of Learning Outcomes 2, 3, 4, and 6 in the Course Outline.

## To do List
   * Read through the presentation
   * Watch the recorded video of the presentation found in the general chat of the Microsoft Team for this course if you did not attend the class when it was presented
   * Review the lesson materials linked below
   * Attempt the MBR recovery listed as the sample exercise for 2022 found on the CIRCL site linked below
   * Do the quiz found under Tests on [Blackboard](https://gc.blackboard.com) for this topic

## Lesson Material
   * [Evidence Analysis Presentation in PDF format](Presentations/NETS1032-21W-05-EvidenceAnalysis.pdf)
   * [Computer Incident Response Center Luxembourg (CIRCL) website with demos, presenatations, sample exercises)](https://www.circl.lu/services/forensic-training-materials/))
   * See [Blackboard](https://gc.blackboard.com) for any available prerecorded video of this presentation under Weekly Learning
   * Links from the presentation slides
      * [File Signature lookup website filesignatures.net](https://filesignatures.net/index.php?search=zip&mode=EXT)
      * [Ransomware filename extensions and discussion](https://www.netfort.com/blog/methods-for-detecting-ransomware-activity/)
      * [Encrypted Disk Detector tool](https://www.magnetforensics.com/free-tool-encrypted-disk-detector/)
      * [Comparison of Encase, FTK, and an old version of Autopsy on Microsoft and Apple filesystem images](http://www.marshall.edu/forensics/files/CERVELLONEADAM_FinalResearchPaper-8-7-2015_-1.pdf)
      * [First part in a youtube video series from UCF describing signatures, carving, and obfuscation](https://www.youtube.com/watch?v=3I1qDfF3T04)
      * [Second part in a youtube video series from UCF describing signatures, carving, and obfuscation](https://www.youtube.com/watch?v=lzU2aY02syg)
      * [Third part in a youtube video series from UCF describing signatures, carving, and obfuscation](https://www.youtube.com/watch?v=ZjtorLc5oZk)
      * [Digital Forensics Truths That Turn Out To Be Wrong - SANS DFIR Summit 2018](https://www.youtube.com/watch?v=gTNo7bv1GZ0)
      * [Report Writing Video describing a format used by the FBI (about 45 minutes)](https://www.youtube.com/watch?v=a4dwypa12c4)
      * [DFIR Summit talk on how a police department does reports for digital forensic investigations](https://www.youtube.com/watch?v=sUwfqk293xU&ab_channel=SANSDigitalForensicsandIncidentResponse)

## Learning Activity
Watch the videos from the presentation, as well as the videos listed under additional resources. The UCF videos are not required to watch in full, but you should watch at least the first 5-10 minutes of each to see what kinds of things they cover. The videos covering truths that turn out to be wrong should be watched in full, as well as the report writing video featuring Dr. Mark Pollitt. Briefly review the materials available at the other websites listed under Additional Resources, primarily check the comparison charts in the white paper comparing Encase, FTK, and Autopsy.
Instead of creating a simulated scenario to investigate, we will be using one we can get online. Do the [CIRCL Sample Investigation listed as **cyberday.lu 2022**](https://www.circl.lu/services/forensic-training-materials/) according to the instructions in the presentation slides provided their website. For this lab, we are focusing on the process of recovering a drive which has had its MBR deleted or damaged maliciously.
When you have recreated the investigation, try creating a forensic report in the same format as described in the video from Dr. Mark Pollitt. If you are unsure whether you have completed these activities correctly, ask the professor to review your work. This activity is not graded.

## Additional Resources    

### General resources
   * [Free Forensic Software List](https://www.secureforensics.com/resources/free-software)
   * [Winhex, windows-only, but integrated into the XWays Forensic tool family](http://winhex.com)
   * [wxHexEditor - multi-platform forensic grade hex editor](https://github.com/EUA/wxHexEditor)
   * [Okteta - a different take on a hex editor designed to support encoding and decoding files](https://utils.kde.org/projects/okteta/)
   * [Windows Search Index Forensics](https://www.edbsearch.com/forensics.html)
   * [Mac forensic tools](https://www.digitalforensics.com/blog/forensic-tools-for-your-mac/)
   * [2-5-1 Storytelling technique for After Action Reviews](https://swanthinks.wordpress.com/2009/11/23/2-5-1-storytelling/)
   * [Physical Image and Partition Mounting in Tsurugi Linux - or how to use ewf image files with command line tools](https://www.youtube.com/watch?v=9uqS7-8At3g)
   * [DOS cipher command reference](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-xp/bb490878(v=technet.10))
   * [APFS features and differences from HFS+](https://www.howtogeek.com/327328/apfs-explained-what-you-need-to-know-apples-new-file-system/)
   * [How to interpret the com.apple.quarantine attribute](https://stackoverflow.com/questions/46198557/understanding-output-of-xattr-p-com-apple-quarantine)

## Graded Activity
This activity is not graded. There is nothing to submit on blackboard for this activity.

## Quiz

The quiz is found on Blackboard under Assignments and Tests.

## Test

There is no separate test for this topic. The quiz will count for your testing mark in this topic.

## Summary
In this module, you have been introduced to analyzing filesystems images.
You should now be:
* Comfortable using analysis tools to extract evidence from Filesystem Images
* Competent to select reporting formats for forensic reports and using those formats
* Familiar with the process for handling evidence obtained from filesystem images

Completing the quiz will provide you with a measure of your knowledge in these areas.
