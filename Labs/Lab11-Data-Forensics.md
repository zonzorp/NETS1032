# NETS1032 Data Forensics Lab
The purpose of this lab is to become acquainted with using steganography tools.

## Install some stego tools
Install some stego tools on a Ubuntu desktop, your Windows laptop, or a Macbook. Many tools are available as packages for Linux. Using Linux as an extraction platform can help protect you from malware hidden in stego files.
* Kali, Parrot, CAINE, and other forensics/hacking distros include some of these and other stego tools in various versions and states.
* Even in these distros, you will likely have to manually add some tools to complete your stegoanalysis toolbox.

## Extract a hidden file from a stegofile
1. Download the [sample image file](whatsinside.jpg) to try with the outguess tool, key for the stegofile is 1234
1. Download the [sample image file](8kscene.jpg) to try with the steghide tool
1. Install steghide outguess
1. Use the appropriate steganalysis tool to examine each stegofile
  * Does it give you evidence that this file is a stegofile?
  * What evidence does it give?
1. Download the other [original cover file](horizon_zero_dawn_london_4k_8k-wide.jpg)
1. Compare the stego file and extracted file for both cases
  * Which of the files is bigger?
  * What can you visually identify as differences in the two images, if anything?
1. Try using the info subcommand of steghide with a passphrase of 1234 on the stegofile
  * Does it tell you what is embedded in the file?
1. Extract the embedded files and try viewing them with an image viewing tool
 
## Create a double layered stegofile
1. Obtain 3 image files to use for your stego exercise
1. Everyone needs to use their own images and duplicates will be rejected
1. The 3 files to use will likely work best with sizes of approximately 30KB, 300KB, and 3MB+ - you may have to try a number of different images to get things to fit
1. Use outguess to hide the smallest file using the middle-sized file as a cover file
1. Use steghide to hide the outguess-encoded stegofile using the largest file as a cover file

## Grading
Submit a single image file which is the steghide-encoded stegofile. Put the password for the inner outguess-encoded image and the outer steghide-encoded image) in the submission comment on blackboard.
