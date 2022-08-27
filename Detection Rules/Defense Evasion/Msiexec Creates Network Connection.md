# Msiexec Creates Network Connection


>About the Rule:

Adversaries may abuse msiexec.exe to proxy execution of malicious payloads. Msiexec.exe is the command-line utility for the Windows Installer and is thus commonly associated with executing installation packages (.msi)
 

>Conditions:

and:

- event.dataset: "endpoint.events.network"
- process.name: "msiexec.exe"
 


>Possible False Positives:

Legitimate msiexec over networks


>Exceptions:

None for now
