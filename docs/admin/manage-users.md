facileManager incorporates the use of multiple user accounts with granular permissions. This way you can limit access to your environment.

You can add, modify, and delete user accounts at **_Admin → Users & Groups_**.

## Local Options
User accounts can be local or from LDAP. For local users, there are some options you can select:

`Force Password Change at Next Login`
>Tick this box the user should be forced to change their password next time they try to login.

`Template User`
>Tick this box if this user should be a template user only. These users cannot be enabled and cannot login to facileManager. Any user account of this type will be depicted with a  next to the user name.

## Permissions
For all users (and groups), each permission checkbox will grant or deny access to certain functionalities within facileManager.

`Super Admin`
>This permission will grant the user unrestricted access to the entire facileManager environment. There must be at least one Super Admin. Any user account with this privilege will be depicted with a  next to the user name.

`Module Management`
>With this permission, the user will be able to activate, deactivate, install, upgrade, and uninstall modules within facileManager.

`User Management`
>This permission allows the user to add, modify, and delete user accounts.

`Run Tools`
>This permission grants the user access to run the various tools in **_Admin → Tools_**.

`Manage Settings`
>This permission grants the user access to change system settings at **_Settings → General_**.

New user accounts can be created quickly from a template by duplicating the template user. This will prompt you for the new username and password while giving you the ability to change any other settings prior to user creation.

User groups can also be created to easily provide the same level of access to multiple user accounts.

_The **User Management** or **Super Admin** permission is required for these actions._

When API Support is enabled at **_Settings → General_**, each user may create an API keypair by editing their user profile. Privileged users will be able change the status of any keypair through **_Admin → Users & Groups_**. This keypair allows the user to authenticate via the API through the client scripts.

--8<--
footer.md
--8<--
