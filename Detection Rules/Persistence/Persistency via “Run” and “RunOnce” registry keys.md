# Persistency via “Run” and “RunOnce” registry keys


>About the Rule:

This rule monitors creation/change of values under the Run/RunOnce keys, which can give persistency for the attacker
 

>Conditions:

and:

- event.category: registry
- registry.key: SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run*
 


>Possible False Positives:

- Installations that requires running code after reboot


>Exceptions:

None for now
