# Unusual Persistence via Services Registry


>About the Rule:

Identifies processes modifying the services registry key directly, instead of through the expected Windows APIs. This could be an indication of an adversary attempting to stealthily persist through abnormal service creation or modification of an existing service.
 

>Conditions:

or:

- registry.path: "HKLM\\SYSTEM\\ControlSet*\\Services\\*\\ServiceDLL"
- registry.path: "HKLM\\SYSTEM\\ControlSet*\\Services\\*\\ImagePath"
 


>Possible False Positives:

- Detailed in the exceptions section


>Exceptions:

or:

- process.executable : ("?:\\Program Files\\*.exe", "?:\\Program Files (x86)\\*.exe", "?:\\Windows\\System32\\svchost.exe", "?:\\Windows\\winsxs\\*\\TiWorker.exe", "?:\\Windows\\System32\\drvinst.exe", "?:\\Windows\\System32\\services.exe", "?:\\Windows\\System32\\msiexec.exe", "?:\\Windows\\System32\\regsvr32.exe")
- (process.name : "procexp??.exe" and registry.data.strings : "?:\\*\\procexp*.sys")
- registry.data.strings : ("?:\\windows\\system32\\Drivers\\*.sys", "\\SystemRoot\\System32\\drivers\\*.sys", "\\??\\?:\\Windows\\system32\\Drivers\\*.SYS", "system32\\DRIVERS\\USBSTOR")