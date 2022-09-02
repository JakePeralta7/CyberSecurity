# Disabling Windows Defender Security Settings via PowerShell


>About the Rule:

Identifies use of the Set-MpPreference PowerShell command to disable or weaken certain Windows Defender settings.
 

>Conditions:

and:

- event.type == "start"
- (process.name : ("powershell.exe", "pwsh.exe", "powershell_ise.exe") or process.pe.original_file_name in ("powershell.exe", "pwsh.dll", "powershell_ise.exe"))
- process.args : "Set-MpPreference"
- process.args : ("-Disable*", "Disabled", "NeverSend", "-Exclusion*")
 


>Possible False Positives:

Defensive systems that fills in the place of windows defender, still need to be investigated in networks where windows defender is not used


>Exceptions:

None for now
