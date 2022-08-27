# Scheduled Task Execution at Scale via GPO


>About the Rule:

Detects the modification of Group Policy Object attributes to execute a scheduled task in the objects controlled by the GPO.
 

>Conditions:

or:

- (event.code: "5136" and winlog.event_data.AttributeLDAPDisplayName:("gPCMachineExtensionNames" or "gPCUserExtensionNames") and winlog.event_data.AttributeValue:(*CAB54552-DEEA-4691-817E-ED4A4D1AFC72* and *AADCED64-746C-4633-A97C-D61349046527*))
- (event.code: "5145" and winlog.event_data.ShareName: "\\\\*\\SYSVOL" and winlog.event_data.RelativeTargetName: *ScheduledTasks.xml and (message: WriteData or winlog.event_data.AccessList: *%%4417*))
 


>Possible False Positives:

- IT guys using GPO to deploy scheduled task widely


>Exceptions:

None for now
