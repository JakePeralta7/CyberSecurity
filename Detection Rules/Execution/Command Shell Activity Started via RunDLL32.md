# Command Shell Activity Started via RunDLL32


>About the Rule:

Identifies command shell activity started via RunDLL32, which is commonly abused by attackers to host malicious code.
 

>Conditions:

and:

- event.type == "start"
- process.name : ("cmd.exe", "powershell.exe")
- process.parent.name : "rundll32.exe"
- process.parent.command_line != null
 


>Possible False Positives:

None for now


>Exceptions:

or:

- process.parent.args : "C:\\Windows\\System32\\SHELL32.dll,RunAsNewUser_RunDLL"
- process.parent.args : "C:\\WINDOWS\\*.tmp,zzzzInvokeManagedCustomActionOutOfProc"
