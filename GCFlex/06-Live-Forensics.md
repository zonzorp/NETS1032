# Live Forensics

## Introduction
This module provides some conceptual and practical information on processes, tools, and considerations for doing examinations of system memory, known as doing live or memory forensics.

For your lab work, ensure you have access to both a Linux desktop environment with root, and a Windows desktop with Administrator. You will be showing your work to the professor throughout the semester, so you will need to be able to share your lab system screen, and the lab system you use will need to be clearly identified as your own (you should use your own name for the login, or at least something unique to you). No marks will be given for showing work on a lab system which is not your own.


## Learning Objectives
At the end of this module, students will:
   * Begin to explore the kinds of artifacts that might be of interest in running system memory
   * Begin using tools for capturing and analyzing images of system memory
   * Demonstrate using forensic analysis tools to identify and extract artifacts of interest from memory images

These objectives are in support of Learning Outcomes 1, 2, 3, 4, and 5 in the Course Outline.

## To do List
   * Read through the presentation
   * Watch the recorded video of the presentation found in the general chat of the Microsoft Team for this course if you did not attend the class when it was presented
   * Review the lesson materials linked below
   * Perform the learning activities as described below
   * Do the quiz found under Tests on [Blackboard](https://gc.blackboard.com) for this topic

## Lesson Material
   * [Live Forensics Presentation in PDF format](Presentations/NETS1032-21W-06-LiveForensics.pdf)
  * See [Blackboard](https://gc.blackboard.com) for any available prerecorded video of this presentation under Weekly Learning
   * Links from the presentation
      * [Belkasoft RAM Capturer tool for Windows](https://belkasoft.com/ram-capturer)
      * [Magnet forensic tools website with link for RAM Capture tool for Windows](http://www.magnetforensics.com)
      * [Redline forensic toolset video](https://www.youtube.com/watch?v=tCIEYCWTdk4&list=PLlv3b9B16Zaf-uDlgouB0DMiPNYU_sJFN&index=3)
      * [Apple's System Integrity Protection and how it impacts forensics](https://en.wikipedia.org/wiki/System_Integrity_Protection)
      * [Linux Memory Extractor (LiME) tool](https://github.com/504ensicslabs/lime)
      * [Volatility memory image analysis tool](https://www.volatilityfoundation.org)
      * [Using VMWare memory files for VM live analysis](https://www.youtube.com/watch?v=P0yw93GJsYU&t=413s)
      * [Fireeye's Redline and Memoryze tools](https://www.fireeye.com/services/freeware.html)
      * [Volatility demo on Windows 10](https://www.youtube.com/watch?v=1PAGcPJFwbE&list=PLlv3b9B16Zaf-uDlgouB0DMiPNYU_sJFN)
      * [SANS DFIR cheat sheets with one for memory forensics](https://www.sans.org/posters/?focus-area=digital-forensics)
      * [The Art of Memory Forensics book, an excellent and very complete book to take you beyond our introduction to this important topic](https://www.memoryanalysis.net/amf)

## Learning Activity
Watch the videos from the presentation, as well as the videos listed under additional resources. Briefly review the materials available at the other websites listed under Additional Resources.
Do the [Live Forensics Assignment](Labs/Lab06-Volatility.md) using the [video from DFIRScience](https://www.youtube.com/watch?v=Uk3DEgY5Ue8&ab_channel=DFIRScience) as a guide for software installation and use.

## Additional Resources    

### Videos with demos of working with RAM captures
   * [5 minute video demonstrating analyzing RAM images using BEC](https://www.youtube.com/watch?v=2gLDGi4jZSY)
   * [LiME demo - Capturing RAM on an AWS Linux EC2 instance](https://www.youtube.com/watch?v=3oto8Bl2vaE&ab_channel=DFIR.Science)
   * [Bento Toolkit for Windows download, install, and demo](https://www.youtube.com/watch?v=PHZxF90sHuM&list=RDCMUCOSFVxvpr3OPiaJSwHWN8BQ&index=2&ab_channel=DFIR.Science)

### Example Software Tools for live forensic analysis
   * [Windows Sysinternals Tools example uses in forensics](https://hakin9.org/incident-security-response-accessenum-free-course-content/)
   * [Belkasoft Evidence Center](https://www.youtube.com/watch?v=mu2mYMOVzyQ)
   * [Comae Stardust memory analysis tools and discussion video](https://www.youtube.com/watch?v=16BSUFKNNjo)
   * [TuxResponse shell script for automated Linux incident response - modifies system being examined in trade for fast response](https://github.com/la3ar0v/TuxResponse)

## Graded Activity
This lab is graded and the lab instructions describe what to submit for it.

## Quiz

The quiz is found on Blackboard under Assignments and Tests.

## Test

There is no separate test for this topic. The quiz will count for your testing mark in this topic.

## Summary
In this module, you have been introduced to working with live memory investigations and capturewd memory images.
You should now be:
* Aware of the uses and limitations of selected forensic tools for investigating the memory of running systems
* Starting on a path to become familiar with the kinds of evidence that can be found in the memory of a running system
* Capable of selecting tools for working with memory images, both hardware and software

Completing the quiz will provide you with a measure of your knowledge in these areas. For the next class you should have your computing environment available with access to both Linux and Windows.

