# Change Password vs Reset Password

Both are used to set new password for an user in Active Directory. The work flow and required permission to execute two methods would be different. Here I have explained what permission will require for what action and what will happen while changing password in both methods.

## Reset Password in Active Directory
  1. Reset Password allows an user to reset (set new password) without providing old password.

  2. Reset password permission requires to the person who resets the password.With AD’s default             permissions, only Administrators and Account Operators can reset passwords.    

  3. When you reset a password you are performing an administrative act, you force the password to be changed without knowing the old password. This can bypass certain rule of the password policy. For example it will bypass the password history but it only bypass the complex password policy, it depends on the password complexity.

  4. When resetting a password, the account will lose access to any EFS protected files that were configured under the user account.

## Change Password in Active Directory
  1. Change Password requires user’s old password to set new password.

  2. The Change password permission requires that the person who changes the password. With AD’s                 default permissions, you can change your own password.  

  3. When you change a password, you supply the old password along with the new password, if the old password is correct and the new password follows the password policy then the password will be changed.

  4. When changing password, the account will not lose any access to any EFS protected files that were configured under the user account.