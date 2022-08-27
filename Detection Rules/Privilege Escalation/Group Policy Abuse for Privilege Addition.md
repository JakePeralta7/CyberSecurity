# Group Policy Abuse for Privilege Addition


>About the Rule:

Detects the first occurrence of a modification to Group Policy Object Attributes to add privileges to user accounts or use them to add users as local admins.
 

>Conditions:

and:

- event.code: "5136"
- winlog.event_data.AttributeLDAPDisplayName:"gPCMachineExtensionNames"
- winlog.event_data.AttributeValue:(*827D319E-6EAC-11D2-A4EA-00C04F79F83A* and *803E14A0-B4FB-11D0-A0D0-00A0C90F574B*)
 


>Possible False Positives:

None for now


>Exceptions:

None for now
