# Lab 2 Examining Microsoft Filesystems
The purpose of this lab is to try using forensic tools to examine Microsoft filesystem images to see what you can recover. It is important to make sure your reports include all relevant evidence, but not irrelevant items or things outside the scope of your investigation.

## Autopsy as a tool for identifying whether pictures of Clint Eastwood are on a suspect drive
In this investigation, we are continuing with our investigation of Donald. We are attempting to determine whether he used the computer to get images of Clint Eastwood from the internet.
1. Download Autopsy and install it, then run it
1. Add the wholedrive image file from lab 1
1. Use the evidence tree to view the filesystems found in the image, and explore them to see what files are in the image
1. Clicking on a file in the file listing allows you to view a file. Use that ability to see if there are any pictures there of Clint Eastwood. If you find any, check the box next to the file with Clint Eastwood, and tag them as notable items.
1. When you have examined all the pictures and tagged all the photos with Clint Eastwood in them, click Generate Report
  * Create the report in html format
1. Open the report by clicking on the file link and review it taking note of what the report contains, and what you would need to add to make it a complete forensic report
Include the report in your submission for this lab.

## Using Prodiscover for identifying evidence of transactions between George Montgomery and Laura Roper
In this investigation, there is an allegation that Laura Roper and George Montgomery worked together. We are looking for evidence that will show whether they had an ongoing business relationship or not. An image file has been captured for us by a 3rd party. We have no access to the third party.
1. Download a copy of [Prodiscover Basic](https://zonzorp.net/ProDiscoverRelease7003Basic.exe)
1. Install Prodiscover Basic and start it
1. Start a new case
1. Add the inChp02.eve image file extracted from [InChp02.exe](https://zonzorp.net/InChp02.exe) self-extracting zip file.
1. Use the Search item in the Prodiscover navigation tree to try finding files with the words George, Montgomery, Laura, or Roper in them.
1. Examine the contents of the found files to see if they do reference George and Laura and if they do, check them off as files of interest with suitable comments about what is in the files you found. Do not include files that aren't relevant to both George and Laura together.
1. Generate a report of your findings that describes the relationship between George and Laura and include that in your submission for this lab.

## Finding Zone.identifier streams using Autopsy
1. Start a new case
1. Add the wholedrive image file you made last week
1. Click in the evidence tree to select drive C, directory catfiles, so that the files show up in the file list on the upper right
1. Repeat the previous step, but use the catfiles directory on drive D
1. Include the following question with your answers in your submission for this lab.
   * What extra files do you see on the D drive in the catfiles directory, compared to the C drive?
   * What is in those extra files?
   * How might you use that information as part of an investigation?

## Examining the registry in an image file using AccessData Registry Viewer
If you have an image capture that includes the system.dat and user.dat files form the windows folder on a c: drive, you can examine the registry in that image. In this scenario, we are trying to determine if a captured registry from an employee's computer has any information which might be useful to a paralegal investigating a Denise Robinson, who works for a competitor, Superior Bicycles.
1. Begin by copying the two registry files to a temporary folder. For this lab, you can download some [sample files](WINDOWS.zip).
1. Extract the system.dat and user.dat files to a temporary folder.
1. Now we are going to look for references to superior bicycles or denise robinson in the registry to see if they left tracks in the registry.
1. Download the [AccessData Registry Viewer](https://www.exterro.com/ftk-product-downloads/registry-viewer-2-0-0) and install it. When you start it, it will ask about a security device for licensing use, just choose No to run in Demo mode.
1. Use File->Open to open the user.dat file you previously downloaded.
1. Use Edit->Find and Edit->Find Next to find the string "superior" and the string "denise" in the registry image.
1. Save a list of the registry keys you found and their contents, and include them in your sumission for this lab.

# Grading
Submit a single PDF file containing your results of doing the 4 investigations in the lab instructions on github.
1. For the first investigation, include the instructions, your activity notes, and a screenshot of the Autopsy window showing the tagged image file(s) in the html report.
2. For the second investigation, include the report of your findings.
3. For the third investigation, include the 3 questions and your answers.
4. For the fourth investigation, include either screenshots of the keys you found with their contents, or a copy-pasted list of them with their contents.
 
# Building on the basics
Our images are trivial. For more interesting images, you could try some of the example investigations detailed at http://dftt.sourceforge.net which is a site for some forensic tool testing.
Windows forensics very commonly includes digging in the registry for artifacts of interest. [This DFIRScience video](https://www.youtube.com/watch?v=bhlGmjOaEl0&ab_channel=DFIRScience) has a brief but solid walkthrough of the [tryhackme.com](https://tryhackme.com) tutorial room covering Windows registry investigations. As the narrator notes several times, the information on tryhackme.com is very much Windows-centric and a bit blind to the bigger world outside of Windows, but he does give a good walkthrough of the room. It highlights important parts of the registry, what is typically supposed to be found where, and what some of the popular tools are for registry-related investigative activity. It is recommended to watch this half-hour video.
