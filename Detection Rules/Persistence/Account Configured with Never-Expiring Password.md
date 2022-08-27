# Account Configured with Never-Expiring Password


>About the Rule:

Detects the creation and modification of an account with the "Don't Expire Password" option Enabled. Attackers can abuse this misconfiguration to persist in the domain and maintain long-term access using compromised accounts with this property.
 

>Conditions:

and:

- event.action:"modified-user-account"
- event.code:"4738"
- message:"'Don't Expire Password' - Enabled"
 


>Possible False Positives:

Dumb IT guys


>Exceptions:

- user.id:"S-1-5-18"
