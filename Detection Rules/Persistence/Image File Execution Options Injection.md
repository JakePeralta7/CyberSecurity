# Image File Execution Options Injection


>About the Rule:

The Debugger and SilentProcessExit registry keys can allow an adversary to intercept the execution of files, causing a different process to be executed. This functionality can be abused by an adversary to establish persistence.
 

>Conditions:

and:

- registry where length(registry.data.strings) > 0
- registry.path : ("HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\*.exe\\Debugger", "HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\*\\Debugger", "HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit\\*\\MonitorProcess", "HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit\\*\\MonitorProcess")
 


>Possible False Positives:

None for Now


>Exceptions:

- registry.data.strings regex~ """C:\\Program Files( \(x86\))?\\ThinKiosk\\thinkiosk\.exe"""
- registry.data.strings regex~ """.*\\PSAppDeployToolkit\\.*"""
