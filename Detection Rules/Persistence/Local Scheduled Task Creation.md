# Local Scheduled Task Creation


>About the Rule:

Indicates the creation of a scheduled task. Adversaries can use these to establish persistence, move laterally, and/or escalate privileges.
 

>Conditions:

and:

- event.type == "creation"
- file.path: "C:\\Windows\\System32\\Tasks\\*"
 


>Possible False Positives:

- Schedule task created by IT
- Software using scheduled task to automate stuff
- Part of the operating system


>Exceptions:

- file.path: “C:\Windows\System32\Tasks\McAfee\McAfee DAT Built in test”
- file.path: “C:\Windows\System32\Tasks\Microsoft\Windows\UpdateOrchestrator\AC Power Download”
