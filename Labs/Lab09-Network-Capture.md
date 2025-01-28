# Lab 08 - Network Data Capture

The purpose of this lab is to practice using different packet capture tools.

## Tcpdump
1. Install tcpdump, tshark, and wireshark if it isn't already present on your nmshost
```bash
sudo apt update
sudo apt install tcpdump tshark wireshark
```
1. Try running tcpdump in live mode to display packets passing over your ens33 interface, stopping it with CTRL-C when you have seen enough
```bash
sudo tcpdump -i ens33
```
1. Start capturing packets from your ens33 interface to a pcap file for later analysis in a terminal window or ssh session
```bash
sudo tcpdump -i ens33 -w ens33.pcap
```
1. While the capture is running, open a browser on nmshost and go to google.
  * Do a search for tcpdump images
  * After the search results display, click the link to see only Images results
  * When the page of thumbnail images finishes loading, stop the capture in the terminal window with CTRL-C.
  * Take note of how many packets were captured.
1. Use tcpdump to read the capture file and display the captured packets in short form, then use wc to count how may lines of output there were (i.e. how many packets it read from the file)
```bash
tcpdump -r ens33.pcap
tcpdump -r ens33.pcap|wc -l
```
1. Try limiting the packets displayed to only http packets on port 80
```bash
tcpdump -r ens33.pcap port http
tcpdump -r ens33.pcap port http|wc -l
```
1. Try displaying the packets which were not on port 80
```bash
tcpdump -r ens33.pcap port not http
tcpdump -r ens33.pcap port not http|wc -l
```
1. Try displaying the packets which were not on port 80 or port 443
```bash
tcpdump -r ens33.pcap port not http and not https
tcpdump -r ens33.pcap port not http and not https|wc -l
```
1. What other protocol might we want to eliminate to find the packets which are not from the common protocols in a web browsing session? Try eliminating that as well and see what is left.
1. Try displaying only the DNS traffic, using IP addresses and port numbers instead of names for those items
```bash
tcpdump -r ens33.pcap -nn port 53
```
1. Try displaying a full packet dump in hexadecimal of the packets that were seen using port 80 in numeric mode
```bash
tcpdump -r ens33.pcap -nn port 80 -X | more
```
1. Try to recreate all of the tcpdump captures and extractions above using tshark and wireshark.
1. Review the [presentation by Andrew McNicol](https://www.slideshare.net/j0b1n/tcpdump-hunter) to see an example of how tcpdump gets used for malware hunting

## Tcpflow
1. Install tcpflow if it isn't already installed
```bash
sudo apt install tcpflow
```
1. Try running tcpflow to capture flows live
```bash
sudo tcpflow -a -i ens33 -e all -o flows
```
1. Surf around some websites with some graphics and multimedia in them to generate some traffic (google, cnn, whatever)
1. Review the files tcpflow created in the flows directory with the file explorer or with a terminal
1. If any are recognizable file types, try opening them
1. Try running the file command on them to see what they contain
1. Try using the more command on them, can you get much from them?
1. Review the report.pdf to see the graphic summary of activity, is it very useful?
1. Try using tcpflow to produce flows from the tcpdump pcap file you captured earlier
```bash
tcpflow -r ens33.pcap -a -e all -o flows2
```
1. Review the files in the flows2 directory to see how it did at breaking out those flows


## Grading
There is nothing to screenshot or submit from this lab. It is not marked.
