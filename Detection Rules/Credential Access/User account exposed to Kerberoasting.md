# User account exposed to Kerberoasting


>About the Rule:

Detects when a user account has the servicePrincipalName attribute modified. Attackers can abuse write privileges over a user to configure Service Principle Names (SPNs) so that they can perform Kerberoasting. Administrators can also configure this for legitimate purposes, exposing the account to Kerberoasting.
 

>Conditions:

and:

- event.action:"Directory Service Changes"
- event.code:5136
- winlog.event_data.ObjectClass:"user"
- winlog.event_data.AttributeLDAPDisplayName:"servicePrincipalName"
 


>Possible False Positives:

None for now


>Exceptions:

None for now
