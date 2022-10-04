# MRS-Explorer
## PowerShell script which renders a GUI for retrieving, auditing, and analyzing Exchange and Exchange Online (Office 365) move request reports from serialized XML data.

As an Exchange and Office 365 delivery consultant, I am often asked to troubleshoot mailbox migrations to help identify why move requests stall or fail.  When using the native Mailbox Replication Service (MRS) for local, cross-forest, or hybrid moves the summary report offers some useful clues but is usually vague and generic for identifying specific issues.  As a result, I often parse the detailed move report using PowerShell or ask a customer to export it to XML for further analysis.

There is actually quite a bit of valuable logging and debug information stored in the detailed move report, but parsing through it all using PowerShell and manually building collections can be quite tedious. I have tried using various XML tools yet found the serialized MRS schema and data simply does not render correctly. Therefore, I developed my own tool to analyze this information.

* Download the script and run it from a local PowerShell console or a connected Exchange remote PowerShell session.
* You may need to set the PowerShell execution policy and/or unblock the script on the file properties after download.
* Script can establish a remote PowerShell session to query Exchange move requests in real-time.  Otherwise, manually export move request XML files for analysis by running the following command from an established Exchange Management Shell or Exchange Online session:
```Get-MoveRequestStatistics username -IncludeReport | Export-CliXml filename.xml```
* To use ADAL/MFA in Exchange Online, connect to remote PowerShell first and then run script from the established session.

![Screenshot](http://blog.zarka.com/wp-content/uploads/2022/10/MRS-Explorer-Screentshot-01.png)
