# Registry Persistence via AppInit DLL


>About the Rule:

Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by AppInit DLLs loaded into processes. Dynamic-link libraries (DLLs) that are specified in the AppInit_DLLs value in the Registry keys HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Windows or HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Windows NT\CurrentVersion\Windows are loaded by user32.dll into every process that loads user32.dll. In practice this is nearly every program, since user32.dll is a very common library.

Similar to Process Injection, these values can be abused to obtain elevated privileges by causing a malicious DLL to be loaded and run in the context of separate processes on the computer. Malicious AppInit DLLs may also provide persistence by continuously being triggered by API activity.

The AppInit DLL functionality is disabled in Windows 8 and later versions when secure boot is enabled.
 

>Conditions:

and:

- registry.path : "HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Windows\\AppInit_Dlls"
- registry.path : "HKLM\\SOFTWARE\\Wow6432Node\\Microsoft\\Windows NT\\CurrentVersion\\Windows\\AppInit_Dlls"
 


>Possible False Positives:

None for now


>Exceptions:

- process.executable : "C:\\Windows\\System32\\msiexec.exe",
- process.executable : "C:\\Windows\\SysWOW64\\msiexec.exe"
- process.executable : "C:\\Program Files\\Commvault\\ContentStore*\\Base\\cvd.exe"
- process.executable : "C:\\Program Files (x86)\\Commvault\\ContentStore*\\Base\\cvd.exe"