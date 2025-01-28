# Lab 09 Network Capture Analysis
The purpose of this lab is to become acquainted with using packet capture analysis tools. We will set up a contrived access to a phishing email as our situation to capture.

### Capture some data to work with
1. Start tcpdump or tshark
   * Run it on the machine you will be doing the email access from so that it sees all the network traffic
   * Run it in a terminal window that only does the capture
   * Save the capture to a file
   * **Leave it running**

```bash
tcpdump -w emailcapture.pcap
```

1. Start Thunderbird or another GUI email client on nmshost, or another VM you set up for this
  * Add an email account: nets1032@zonzorp.net, email your professor for the password to use
  * Let it figure out the connection config, but click Manual config after it makes a guess, and before saving it
    * Turn off TLS/SSL for the IMAP connection, set it to None - Thunderbird will warn you it is insecure, but go for it anyway
    * Save the config, and when Thunderbird starts up, open the Paypal folder and view the message in the folder - *screenshot*
  * **DO NOT DELETE THE MESSAGE, your classmates will need to be able to view it**

1. Stop the tcpdump so that you have a usable `emailcapture.pcap` file - *screenshot*

### Use tcpflow to break out the flows into separate files
1. Run tcpflow with full scanners to create separate flow files - *screenshot*
```bash
tcpflow -r emailcapture.pcap -a -e all -o emailflows
```

1. Identify the flow file which contains the IMAP login. *Hint - look for the word Authenticate in the flow file using grep* - *screenshot*
1. Use base64 decode on the login string to decode the login and password combination like you saw in the video - *screenshot*
```bash
base64 -d <<<"ugly long string on line after Authenticate in flow"
```

### Use ngrep to find interesting flows
1. Run ngrep to browse the IMAP session in the capture file
```bash
ngrep -I emailcapture.pcap -W byline -q port 143 | more
```
1. Create an ngrep command to find the Authentication information instead of the whole imap session - *screenshot*

1. As a comparison, try using ngrep to view live traffic while retrieving the icanhazip.com website, displaying only http traffic in byline mode - *screenshot*

### Use splitcap to manage large captures
1. Use splitcap to make separate files for the flows on port 143 - *screenshot*

#### Reflection questions to be included in your project submission
3. How do the flow files from splitcap differ from the flow files from tcpflow?
4. Which one is easier to work with to extract the IMAP login?
5. What commands did you use to extract the login from the tcpflows, versus the splitcap flows?

### Use tcpstat to recognize interesting activity
1. Run tcpstat to display the session activity timeline - *screenshot*
```bash
tcpstat -r emailcapture.pcap -o "Time: %r. \tbps: %b\tpps: %p\tARP: %A. \tTCP: %T.  \tUDP: %U.  \tSizes: %m-%M\n"
```

#### Task to be included in your project submission
1. Identify if possible
   * delays in the session
   * when large transfers occurred
   * when data bursts happened

### Use NetworkMiner to explore a capture
1. Install NetworkMiner and open your capture file
1. Review the various tabs of discovered information
1. Note the display of the login credentials for the IMAP session - *screenshot*
1. After running NetworkMiner, review the files it put into the AssembledFiles and Images directories
1. Select 2 capture files from the sample captures on netresec.com to open with NetworkMiner and see what it shows they contain
   * include at least one screenshot showing something interesting from both of the pcaps you looked at
   * describe what you found interesting about the ones you selected

## Grading
Submit a single pdf file containing screenshots as well as text responses to the questions in the lab. Use the rubric on blackboard as a guide to ensure you have everything needed in your submission.
