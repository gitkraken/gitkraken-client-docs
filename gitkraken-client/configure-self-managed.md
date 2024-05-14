---

title: Configure GitKraken Self-Hosted Server
description: Instructions for configuring GitKraken Self-Hosted Server
taxonomy:
    category: gitkraken-client

---

After installing GitKraken Self-Hosted Server (AKA Enterprise Self-Hosted), you are ready to configure the Server.

***

<a id="server-license"></a>

### Server License
Browse to your GitKraken Self-Hosted server:
<img src='/wp-content/uploads/select-license.png' srcset='/wp-content/uploads/select-license@2x.png' class='img-bordered img-responsive center'>

Select _Browse for license_ file and browse to the the license file that was provided to you with the GitKraken Self-Hosted installation files.  Once selected, the license file will show you the details of your license:
<img src='/wp-content/uploads/license-details.png' srcset='/wp-content/uploads/license-details@2x.png' class='img-bordered img-responsive center'>

<a id="authentication"></a>

### Authentication
Select the Authentication Config for your server:

  * Built-in: Users will be authenticated using an email address and password
  * LDAP: Users will be authenticated using LDAP
<img src='/wp-content/uploads/auth-config.png' srcset='/wp-content/uploads/auth-config@2x.png' class='img-bordered img-responsive center'>

If you're using Built-in authentication, [jump](#smtp-server) to the next step.

<a id="ldap-configuration"></a>

#### LDAP Configuration
Provide the hostname and port for your LDAP server.
<img src='/wp-content/uploads/ldap-host-port.png' srcset='/wp-content/uploads/ldap-host-port@2x.png' class='img-bordered img-responsive center'>

Select the encryption method.  This should correspond with the port entered above.
<img src='/wp-content/uploads/encryption-method.png' srcset='/wp-content/uploads/encryption-method@2x.png' class='img-bordered img-responsive center'>

Assign the Base Distinguished Names, Access Group, and Admin Group Common Names.

  * **Base Distinguish Names** - These are the top-level locations used to search in your directory

  * **Access Group Common Names** - Used to specify the group name whose users will be granted licenses for GitKraken.  If no access group is specified, all users found will be granted a license.

  * **Admin Group Common Names** - Used to specify the group name whose users will be granted admin access to the GitKraken Self-Hosted site.  If no admin group is specified, no users found will be granted admin rights.
<img src='/wp-content/uploads/base-dn.png' srcset='/wp-content/uploads/base-dn@2x.png' class='img-bordered img-responsive center'>

Assign the user attributes needed to identify LDAP users.

  * **Username Attribute** (Required) - Used to map to the user's username in GitKraken.

  * **Email Attribute** (Required) - Used to map to the user's email in GitKraken.

  * **Name Attribute** - Used to map to the user's name in GitKraken.

<img src='/wp-content/uploads/user-attributes.png' srcset='/wp-content/uploads/user-attributes@2x.png' class='img-bordered img-responsive center'>

Provide the Distinguished Name for the user that will be used to search LDAP for users and groups.  
This can be a separate user that only has rights to search LDAP.  
*This user is required when anonymous binding in LDAP is disabled.*
<img src='/wp-content/uploads/search-user.png' srcset='/wp-content/uploads/search-user@2x.png' class='img-bordered img-responsive center'>

<div class='callout callout--warning'>
  <p>Note: The Domain Search Password field will display blank, even when the field is set.</p>
</div>

Enable the sync server, if desired, and set the sync interval.  The sync server will automatically search LDAP at the set interval and update GitKraken licenses accordingly.

If the sync server is not enabled, you will need to manually manage user accounts.
<img src='/wp-content/uploads/sync-server.png' srcset='/wp-content/uploads/sync-server@2x.png' class='img-bordered img-responsive center'>

<a id="smtp-server"></a>

### SMTP Server
An SMTP server is required, unless LDAP authentication is in use.

Set the SMTP server IP address or hostname, the _SMTP port_, and the _From Address_.  If your SMTP server needs a secure connection, check the box for secure protocols and provide the username and password, if needed.  The test connection button will allow you to verify the connection information is accurate:
<img src='/wp-content/uploads/smtp-setup.png' srcset='/wp-content/uploads/smtp-setup@2x.png' class='img-bordered img-responsive center'>

<a id="super-user"></a>

### Super User
The super user will be the Owner of the GitKraken Self-Hosted license.  The super user does not consume a license, cannot log into GitKraken Desktop, and cannot be changed or viewed from the account site user management page.
<img src='/wp-content/uploads/super-user.png' srcset='/wp-content/uploads/super-user@2x.png' class='img-bordered img-responsive center'>

<div class='callout callout--neutral'>
  <p>Note: Visit the <a href="/enterprise/upgrade-enterprise/#reset-the-super-user-password">upgrade page</a> to see how to reset the super user password.</p>
</div>

Configuration is complete!  You should now be at the 'Manage Users' screen where you can begin adding users to GitKraken Self-Hosted.
<img src='/wp-content/uploads/manage-users.png' srcset='/wp-content/uploads/manage-users@2x.png' class='img-bordered img-responsive center'>

<a id="adding-users"></a>

### Adding Users
To add a user click on the Add user button and provide the email address of the user:
<img src='/wp-content/uploads/user-email.png' srcset='/wp-content/uploads/user-email@2x.png' class='img-bordered img-responsive center'>

By default, users can create an account themselves from the GitKraken Self-Hosted site.  If you don't want to allow this functionality you can click the Registration tab on the left.  
<img src='/wp-content/uploads/registration-settings.png' srcset='/wp-content/uploads/registration-settings@2x.png' class='img-bordered img-responsive center'>
