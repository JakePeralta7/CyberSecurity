# Potential Modification of Accessibility Binaries


>About the Rule:

Windows contains accessibility features that may be launched with a key combination before a user has logged in. An adversary can modify the way these programs are launched to get a command prompt or backdoor without logging in to the system.
 

>Conditions:

and:

- event.type in ("start", "process_started", "info")
- process.parent.name : ("Utilman.exe", "winlogon.exe")
- user.name == "SYSTEM"
- process.args : ( "C:\\Windows\\System32\\osk.exe", "C:\\Windows\\System32\\Magnify.exe", "C:\\Windows\\System32\\Narrator.exe", "C:\\Windows\\System32\\Sethc.exe", "utilman.exe", "ATBroker.exe", "DisplaySwitch.exe", "sethc.exe" )
 


>Possible False Positives:

None for now

>Exceptions:

- process.pe.original_file_name in ( "osk.exe", "sethc.exe", "utilman2.exe", "DisplaySwitch.exe", "ATBroker.exe", "ScreenMagnifier.exe", "SR.exe", "Narrator.exe", "magnify.exe", "MAGNIFY.EXE" )
- process.code_signature.subject_name == "Microsoft Windows"
- process.code_signature.status == "trusted"
