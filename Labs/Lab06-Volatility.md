# Memory Forensics with Volatility

1. Install a memory dump tool of your choice
1. Capture a memory dump of your windows 10 machine
1. Install the volatility tool from [the volatility foundation website](https://volatilityfoundation.org), their github repo has installation info.
1. Use Volatility3 to perform the following tasks using volatility subcommands:
   1. Ensure it can identify the OS version using windows.info.Info *screenshot*
   1. Produce a list of processes running using windows.pslist *screenshot*
   1. Produce the hivelist using windows.registry.hivelist *screenshot*
   1. Produce a credentials list using windows.hashdump to see if you can retrieve the password hashes *screenshot*
   1. Produce the network connections table using windows.netstat *screenshot* (try netscan instead if netstat isn't there or doesn't work for you)- describe any interesting or unexpected connections *screenshot and write up a brief description of any connections you did not expect or found interesting*
1. Submit your results as a single pdf file on blackboard
   * **DO NOT INCLUDE FULL OUTPUT LISTINGS FROM VOLATILITY, only the volatility command and the first screenful of output from it for each command**
   * DO INCLUDE the volatility output lines that support your response to the network connections question above

## Grading
This assignment is graded and counts towards your mark for the course. Submit the screenshots listed above either as separate files (NOT A ZIP), or images in a PDF file. Your response to the network connections found must be submitted either as a text file (.txt, NOT WORD DOC OR DOCX), or as part of a PDF you are submitting that includes your screenshots. Be sure your screenshots are readable. If they have fonts too tiny for blackboard to display, I cannot give you marks for them.
