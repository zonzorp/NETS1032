# Network Device Forensics

This lab is intended to give you practice looking for configuration changes on a router which may indicate compromise.

## Examining pfsense router configuration backups
1. Download the following pfsense configuration backup files to your local disk.
    1. [backup 1](config-pfSense.localdomain-20250325235114.xml)
    1. [backup 2](config-pfSense.localdomain-20250325235906.xml)
    1. [backup 3](config-pfSense.localdomain-20250326000210.xml)
    1. [backup 4](config-pfSense.localdomain-20250326000353.xml)
    1. [backup 5](config-pfSense.localdomain-20250326000625.xml)
1. For each of the downloaded config backup files, review the configuration in the backup to determine if there are unusual settings which may indicate compromise. Some of the kinds of things you should be checking for could include the following:
    1. Look for obviously invalid or unusable IP addresses
    1. Look for suspicious services configured
    1. Look for accounts which are suspicious
    1. Look for administrative access which does not appear normal
    1. Look for credentials which are suspicious

## Grading
Submit a single PDF file with your comments about what might be compromised for each of the 5 backup files. Include supporting configuration information and data from the backup xml files to support your comments.
