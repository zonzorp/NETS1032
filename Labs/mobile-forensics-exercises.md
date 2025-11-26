# Practive activities for mobile forensics

## Exercise 1 - Basic data extraction using Andriller

In this lab, we’ll perform a basic data extraction from an Android emulator using Andriller. The goal is to familiarize you with the extraction process and the type of data that can be retrieved.

### Steps:
1.	Install an Android emulator such as Android Studio or Genymotion on your virtual machine.
1.	Launch the emulator and create a new virtual device.
1.	Populate the virtual device with sample data (e.g., contacts, messages, photos).
1.	Launch Andriller and select the emulator as the connected device.
1.	Perform a full logical extraction.
1.	Review the extracted data.

## Exercise 2 - Analyzing Extracted Data with Autopsy

After extracting data, the next step is analysis. In this lab, we will use Autopsy to analyze the data extracted from the previous exercise.

### Steps:
1.	Open Autopsy and create a new case.
1.	Import the extracted data from Andriller.
1.	Navigate through the data, looking for significant artifacts (e.g., call logs, messages, photos).
1.	Document your findings in a report.

## Exercise 3 - Identifying Malware with Mobile Verification Toolkit (MVT) on an Emulator
For educational purposes, you can use a known and safe malware APK designed specifically for training and testing in a controlled environment.

### Examples
1.	DroidBench:
	•	Description: DroidBench is a collection of Android applications designed to test the effectiveness of Android security analysis tools. These applications contain various types of vulnerabilities, including those that can be exploited by malware.
	•	Link: [DroidBench GitHub](https://github.com/secure-software-engineering/DroidBench)￼
1.	InsecureBankv2:
	•	Description: InsecureBankv2 is an intentionally insecure Android app developed for security professionals to learn and practice mobile application security analysis.
	•	Link: [InsecureBankv2 GitHub](https://github.com/dineshshetty/Android-InsecureBankv2)￼
1.	Diva (Damn Insecure and Vulnerable App):
	•	Description: DIVA is a vulnerable Android app developed by Payatu, designed to help users understand and practice different types of vulnerabilities that can be found in Android applications.
	•	Link: [Diva GitHub](https://github.com/payatu/diva-android)￼

### Identifying Malware with Mobile Verification Toolkit (MVT) on an Emulator
Malware analysis is a crucial part of mobile forensics. This lab will guide you through identifying potential malware on an Android emulator using MVT.

Steps:
1.	Use the same emulator from the first lab exercise.
1.	Download the APK file of one of the above malware samples (e.g., DroidBench, InsecureBankv2, or Diva) to your virtual machine.
1.	Install the malware APK on the emulator:
	•	Enable developer options on the emulator.
	•	Install the APK using the following command in the terminal: adb install /path/to/malware.apk
1.	Run MVT and scan the emulator for known malware signatures:
	•	Launch MVT on your Kali Linux.
	•	Use the command mvt-android scan -i /path/to/emulator/data
1.	Analyze the scan results and identify any suspicious activities or files.
1.	Document the findings and recommend next steps for mitigation.

###vImportant Notes:
	•	Ensure you are using these tools in a controlled and isolated environment to prevent any unintended consequences.
	•	Never use real malware in a production or non-isolated environment.
	•	Always follow ethical guidelines and legal requirements when working with malware samples.

This setup will provide a safe and educational experience for students learning about mobile forensics and malware analysis.