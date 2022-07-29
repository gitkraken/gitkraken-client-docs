---

title: Single Sign On
description: How to enable and use Single Sign On (SSO)
taxonomy:
    category: gitkraken-client

---

Single Sign On (SSO) is an easy way to sign in to mutliple different applications using one authentication method. 

From <a href='https://en.wikipedia.org/wiki/Single_sign-on' target='_blank'>Wikipedia</a>:
*“Single sign-on is an authentication scheme that allows a user to log in with a single ID to any of several related, yet independent, software systems. True single sign-on allows the user to log in once and access services without re-entering authentication factors.”*

Once your organization has setup SSO with an Identity Provider (IdP), the Owner/Admin on your GitKraken organization can link your orgazation to that identity provider. Then, any users associated with your IdP can login to GitKraken apps and services with a single click. 🎉

<div class='callout callout--warning'>
    <p><strong>Note:</strong> You must have an active GitKraken Teams or Enterprise License to enable SSO</p>
</div>

***

## SSO in GitKraken


GitKraken is a third party application so, we don’t have to worry about how the users are created on the Identity Provider (Idp: okta, azure etc), or the groups they belong to. We just have to initiate an oauth authentication flow with the IdP. For doing so, we need to know what IdP we should use, and we will need some data about the IdP.


### Supported Identity Providers

The following IdPs are supported by GitKraken:

* <a href='https://azure.microsoft.com/' target='_blank'>Azure AD</a>
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>G Suite</a>
* <a href='https://www.pingidentity.com/en.html' target='_blank'>Ping Identity</a>


○ <a href='https://azure.microsoft.com/' target='_blank'>Azure AD</a>
○ Okta
○ G Suite
○ Ping Identity


### License Requirements

Single Sign On is only availibe as part of the teams and enterprise plans <a href='https://www.gitkraken.com/git-client/pricing' target='_blank'>teams and enterprise plans</a> 


### Setting up SSO on a GitKraken Organization



SSO is set up at an Organization level, and for each organization we can have multiple IdP.
SSO just can be set up by users with the roles: Owner or Admin. 


How to set up SSO:

1. <a href='https://app.gitkraken.com/' target='_blank'>Login</a> to GitKraken and navigate to the organization you want to enable SSO for.
2. On the left menu click on SSO (if you can’t see this menu: check that: you are logged in with an user that is the org Owner or an Admin, and also check if the organization has a Teams or Enterprise subscription plan).

<div class='callout callout--warning'>
    <p>If you do not see the SSO option, confirm that: you are logged in as the Owner or an Admin for this organization, your organization has either a Teams or Enterprise subscription</p>
</div>

3. Click the `Endable SSO` checkbox and you will be presented with some additional fields.

**Organization Domain Name:** The domain that is used for everyone who want to use SSO to login. 

this is the domain that each and every mail user that belongs to this organization and wants to use SSO must have. For instance, in the example above this organization Domain is: nurias.domain.com so the users that belong to this organization and want to use SSO must have email address that belongs to this domain, for example: john@nurias.domain.com, katherin@nurias.domain.com etc. Otherwise if a user with an email that doesn’t belong to this domain, that also belongs to this gitKraken organization won’t be able to use SSO for logging in, (he/she should use other login methods like, user/password, login with github etc).R2FwbEdCZWxid1Z0M0FYdnRHNUpydz09

There is just one domain allowed per Organization, and it must be unique. The accounts site doesn’t allow to use a domain that is being used by another organization.

**JIT, Enable Just In Time Provisioning:** if this field is checked, when a user logs in into the Accounts Site for the first time, without having a license, using SSO with an email which domains belong to a gitKraken org. If there is any available license in the gitkraken org he/she will be automatically given one. 

Click on “Save Data”, for storing the SSO configuration. Once that is completed, you will see the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button appear.

4. Click the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button to setup the connection between your GitKraken Organization and the Identity Provider.

Here you will see a list of all of the currently setup SSO connections, since multiple can be setup simultaneously. 

### Add SSO Connection using Metadata

Click on <button class='button button--success button--ui button--nolink'>Add Using Metadata</button> and you will see the following fields:

**Identity Provider:** choose a [supported provider](/gitkraken-client/single-sign-on/#supported-identity-providers) from the drop-down.
**IdP Metadata URL /IdP Metadata:** depending on the  IdP we can use one or both of thse options for setting up the SSO connection. 

Example 1: setting up Otka

Okta is configured by using a metadata file.
1. Access your Okta instance
2. Go to the Application that you want to use
3. Click on “Sign on” and scroll down to SAML Signing Certificates:

<img src="/wp-content/uploads/sso-okta-certs.png" class="img-bordered img-responsive center">

4. Notice that there is just one Active. Click on Actions, (on the one that is active).

<img src="/wp-content/uploads/sso-okta-certs-actions.png" class="img-bordered img-responsive center">

5. Click on *Download certificate* and you will be prompted with an xml file.
6. Copy this file content and paste it into the *IdP metadata* field.
7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” to not automatically enable this connection and prevent users from using it.

<img src="/wp-content/uploads/sso-okta-paste-metadata.png" class="img-bordered img-responsive center">

Example 2: setting up Azure

1. Access to your Azure account, and go to Active Directory -> Enterprise Applications

<img src="/wp-content/uploads/sso-azure-applications.png" class="img-bordered img-responsive center">

2. Click on the application that you want to use
3. On the left menu select “Single Sign-on”
4. Scroll down to the section: “ SAML Signing Certificate”

<img src="/wp-content/uploads/sso-azure-saml-cert.png" class="img-bordered img-responsive center">

5. Copy the “App Federation Metadata Url”
6. Go to Gitkraken and paste this URL on the “Idp metadata URL”:

<img src="/wp-content/uploads/sso-azure-saml-cert.png" class="img-bordered img-responsive center">

7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” to not automatically enable this connection and prevent users from using it.


<div class='callout callout--none'>
    <p><strong>Note:</strong> “Just in time provisioning” and the “Domain” are the same for all connections in an organization.</p>
</div>

## Logging in to GitKraken with SSO

For a user to be able to log in into the Accounts Site using SSO, one of the following situations must happen:
The user has an account that: has a license on an Organization that has SSO set up, his/her email address domain matches the Organization’s domain and the IdP configured for the GitKraken org allows this user to log in.
The user does not have an account but: his/her email address domain matches a domain of one of GitKraken’s organizations that has SSO set up and this user is allowed by the IdP (Identity provided server). And The GitKraken Org allows just in time provisioning and there is an available license.

## Troubleshooting / Error Messages
