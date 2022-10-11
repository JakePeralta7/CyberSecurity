# Understanding the Logs

Active Directory build-in change auditing events categorized under following three policy settings.
- Audit account management
- Audit directory service access
- Audit directory service changes (available only from Win 2008 R2 or later)

## Audit account management

The Audit account management events provides the high level auditing of user,computer and group maintenance changes. This policy events also categorized as following ways.

- User Account Management
- Computer Account Management
- Security Group Management
- Distribution Group Management

1. User Account Management

    The following table document lists the event IDs of the user account management category.
 

    | Event ID	| Reason
    |-----------|-
    | 4720	    |A user account was created.
    |4722	    |A user account was enabled.
    |4723	    |An attempt was made to change an account’s password.
    |4724	    |An attempt was made to reset an accounts password.
    |4725	|A user account was disabled.
    |4726	|A user account was deleted.
    |4738	|A user account was changed.
    |4740	|A user account was locked out.
    |4767	|A user account was unlocked.
    |4780	|The ACL was set on accounts which are members of administrators groups.
    |4781	|The name of an account was changed.
    |4794	|An attempt was made to set the Directory Services Restore Mode administrator password
    |5376	|Credential Manager credentials were backed up.
    |5377	    |Credential Manager credentials were restored from a backup.

2. Computer Account Management

    The following table document lists the event IDs of the Computer Account Management category.

    | Event ID  | Reason
    |-----------|-
    |4741	    |A computer account was created.
    |4742	    |A computer account was changed.
    |4743	    |A computer account was deleted.

3. Security Group Management

    The following table document lists the event IDs of the Security Group Management category.


    | Event ID  | Reason
    |-----------|-
    |4727	    |A security-enabled global group was created.
    |4728	    |A member was added to a security-enabled global group.
    |4729	    |A member was removed from a security-enabled global group.
    |4730	    |A security-enabled global group was deleted.
    |4731	    |A security-enabled local group was created.
    |4732	    |A member was added to a security-enabled local group.
    |4733	    |A member was removed from a security-enabled local group.
    |4734	    |A security-enabled local group was deleted.
    |4735	    |A security-enabled local group was changed.
    |4737	    |A security-enabled global group was changed.
    |4754	    |A security-enabled universal group was created.
    |4755	    |A security-enabled universal group was changed.
    |4756	    |A member was added to a security-enabled universal group.
    |4757	    |A member was removed from a security-enabled universal group.
    |4758	    |A security-enabled universal group was deleted.
    |4764	    |A groups type was changed.

4. Distribution Group Management

    The following table document lists the event IDs of the Distribution Group Management category.

    | Event ID  | Reason
    |-----------|-
    |4744	    |A security-disabled local group was created.
    |4745	    |A security-disabled local group was changed.
    |4746	    |A member was added to a security-disabled local group.
    |4747	    |A member was removed from a security-disabled local group.
    |4748	    |A security-disabled local group was deleted.
    |4749	    |A security-disabled global group was created.
    |4750	    |A security-disabled global group was changed.
    |4751	    |A member was added to a security-disabled global group.
    |4752	    |A member was removed from a security-disabled global group.
    |4753	    |A security-disabled global group was deleted.
    |4759	    |A security-disabled universal group was created.
    |4760	    |A security-disabled universal group was changed.
    |4761	    |A member was added to a security-disabled universal group.
    |4762	    |A member was removed from a security-disabled universal group.
    |4763	    |A security-disabled universal group was deleted.

## Audit directory service access
Audit directory service access events provides the low-level auditing for all types of objects in AD. Directory service access events not only logs the information of an object that was accessed and by whom but also logs exactly which object properties were accessed.

The following table document lists the event IDs of the Distribution Group Management category.

| Event ID  | Reason
|-----------|-
|4661	    |A handle to an object was requested
|4662	    |An operation was performed on an object.
|5139	    |A directory service object was moved.

## Audit Directory Service Changes
The events which are comes under this category includes the extra details like Old Value and New Value of the changed properties.This Advanced Audit Policy comes under the subcategory of  Directory Service Access.

The following table document lists the event IDs of the Directory Service Changes subcategory.

| Event ID	| Reason
|-----------|-
|5136	    |A directory service object was modified.
|5137	    |A directory service object was created.
|5138	    |A directory service object was undeleted
|5139	    |A directory service object was moved.
|5141	    |A directory service object was deleted.