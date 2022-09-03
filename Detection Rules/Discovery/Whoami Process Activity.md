# Whoami Process Activity


>About the Rule:

Identifies suspicious use of whoami.exe which displays user, group, and privileges information for the user who is currently logged on to the local system.
 

>Conditions:

and:

- event.type in ("start", "process_started")
- process.name: "whoami.exe"
- process.args in ("*/groups*", "*/all*", "*/priv*", "*/fqdn*", "*/user*")


>Possible False Positives:

None for Now


>Exceptions:

- process.parent.executable : ("C:\\Program Files\\Microsoft Monitoring Agent\\Agent\\MonitoringHost.exe", "C:\\Program Files\\Cohesity\\cohesity_windows_agent_service.exe")
