# Creation of a Hidden Local User Account


>About the Rule:

Identifies the creation of a hidden local user account by appending the dollar sign to the account name. This is sometimes done by attackers to increase access to a system and avoid appearing in the results of accounts listing using the net users command.
 

>Conditions:

- registry.path : "HKLM\\SAM\\SAM\\Domains\\Account\\Users\\Names\\*$\\"
 


>Possible False Positives:

None for Now


>Exceptions:

None for now
