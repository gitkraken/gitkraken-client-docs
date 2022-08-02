---

title: Single Sign On (SSO)
description: How to enable and use Single Sign On (SSO)
taxonomy:
    category: gitkraken-client

---

Single Sign On (SSO) is an easy way to sign in to mutliple different applications using one authentication method. 

Once your organization has setup SSO with an Identity Provider (IdP), the Owner/Admin on your GitKraken organization can link your orgazation to that identity provider. Then, any users associated with your IdP can login to GitKraken apps and services with a single click. 🎉

<div class='callout callout--warning'>
    <p><strong>Note:</strong> You must have an active GitKraken Teams or Enterprise License to enable SSO</p>
</div>
## What is SSO?

Let’s first review the <a href='https://en.wikipedia.org/wiki/Single_sign-on' target='_blank'>Wikipedia</a> definition of SSO:

*“Single sign-on is an authentication scheme that allows a user to log in with a single ID to any of several related, yet independent, software systems. True single sign-on allows the user to log in once and access services without re-entering authentication factors.”*

<img src="/wp-content/uploads/sso-example-diagram.png" class="img-bordered img-responsive center">

The above diagram depicts what a typical SSO setup entails. These are the applications or actors involved in the setup:

**Directory Server:**  A Directory Server is an application that stores information about the “objects” that belong to an organization. An object can be: printers, computers, shared folders, users, groups (a group is just a group of users). Some objects can contain other objects, which then allows them to reflect hierarchical structures.  

Examples of Directory Server applications are:
* <a href='https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/ad-ds-getting-started' target='_blank'>Microsoft Active Directory</a> 
* <a href='https://www.oracle.com/oem/id-mgmt/idm-mgmt.htmlanagement/governance/' target='_blank'>Oracle Identity Governance (OIG) Suite</a> 
* <a href='https://jumpcloud.com/' target='_blank'>Jump Cloud</a> 

**Identity Provider:**  An identity provider (abbreviated IdP or IDP) is a system entity that creates, maintains, and manages identity information for principals and also provides authentication services to relying applications within a federation or distributed network. An IdP provider stores 3 main components: Users, Groups, and Applications.

Examples of Identity Provider applications are:
* <a href='https://azure.microsoft.com/' target='_blank'>Azure Active Directory</a> 
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>Google Identity Platform</a>

The Identity Providers provide services that allow third party applications to authenticate their users. 
The authentication mechanism they provide is called “Oauth”, which allows third party applications to authenticate users without accessing/storing their password. 

***
## SSO in GitKraken

GitKraken is a third party application so, we don’t have to worry about how the users are created on the Identity Provider (Idp: okta, azure etc), or the groups they belong to. We just have to initiate an oauth authentication flow with the IdP. For doing so, we need to know what IdP we should use, and we will need some data about the IdP.

### Supported Identity Providers

GitKraken may initiate an Oauth authentication flow with the following supported Identity Providers (IdPs):

* <a href='https://azure.microsoft.com/' target='_blank'>Azure Active Directory</a> 
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>Google Identity Platform</a>
* <a href='https://www.pingidentity.com/en.html' target='_blank'>Ping Identity</a>

<div class='callout callout--warning'>
    <p><strong>Note:</strong> Your IdP(s) will first need to be configured before setting up the connection in GitKraken. For assistance please contact your IdP administrator or consult the IdP documentation for help.</p>
</div>

### License Requirements

Single Sign On is only availibe as part of the <a href='https://www.gitkraken.com/git-client/pricing' target='_blank'>teams and enterprise plans</a>. 

### Setting up SSO on a GitKraken Organization

* SSO is set up at the Organization level. Each organization can have 0,1, or many IdPs connected simultaneously.
* SSO can only be setup by the Owner or by an Admin of the organization. 


How to set up SSO:

1. <a href='https://app.gitkraken.com/' target='_blank'>Login</a> to GitKraken and navigate to the organization you want to enable SSO for.
2. On the left menu click on SSO (if you can’t see this menu: check that: you are logged in with an user that is the org Owner or an Admin, and also check if the organization has a Teams or Enterprise subscription plan).

<div class='callout callout--warning'>
    <p>If you do not see the SSO option, confirm that: you are logged in as the Owner or an Admin for this organization, your organization has either a Teams or Enterprise subscription</p>
</div>

3. Click the `Endable SSO` checkbox and you will be presented with some additional fields.

**Organization Domain Name:** The domain that is used for everyone who wants to use SSO to login. Each user must have a matching domain in their email address and must be defined in the IdP.

this is the domain that each and every mail user that belongs to this organization and wants to use SSO must have. For instance, in the example above this organization Domain is: nurias.domain.com so the users that belong to this organization and want to use SSO must have email address that belongs to this domain, for example: john@nurias.domain.com, katherin@nurias.domain.com etc. Otherwise if a user with an email that doesn’t belong to this domain, that also belongs to this gitKraken organization won’t be able to use SSO for logging in, (he/she should use other login methods like, user/password, login with github etc).R2FwbEdCZWxid1Z0M0FYdnRHNUpydz09

There is just one domain allowed per Organization, and it must be unique. The accounts site doesn’t allow to use a domain that is being used by another organization.

**JIT, Enable Just In Time Provisioning:** This allows users in this domain to login with their email and be automatically provisioned a license. In order for a user to be automatically given a license:

* Just in time provisioning must be enabled (JIT option checked)☑ .
* The user email must be part of the SSO domain on the IdP.
* There must be an availible licence on the GitKraken Organization.

if this field is checked, when a user logs in into the Accounts Site for the first time, without having a license, using SSO with an email which domains belong to a gitKraken org. If there is any available license in the gitkraken org he/she will be automatically given one. 

Click on “Save Data”, for storing the SSO configuration. Once that is completed, you will see the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button appear.

4. Click the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button to setup the connection between your GitKraken Organization and the Identity Provider.

Here you will see a list of all of the currently setup SSO connections, since multiple can be setup simultaneously. 

### Add SSO Connection using Metadata

Click on <button class='button button--success button--ui button--nolink'>Add Using Metadata</button> and you will see the following fields:

**Identity Provider:** choose a [supported provider](/gitkraken-client/single-sign-on/#supported-identity-providers) from the drop-down.
**IdP Metadata URL /IdP Metadata:** depending on the  IdP we can use one or both of thse options for setting up the SSO connection. 
**Don't enable this conenction immediately** ✅ by default new connections are automatically enabled. This checkbox will create the connection but users will not be able to login using SSO with this IdP until it is enabled.

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

## Logging in using SSO

When logging into GitKraken Client, GitLens, <a href='https://account.gitkraken.com/account-info' target='_blank'>account.gitkraken.com</a> , or anywhere else to access your GitKraken account, you should see the `Sign In with SSO` option.

<img src="/wp-content/uploads/sso-sign-in.png" class="img-bordered img-responsive center">

After clicking “Sign in with SSO”, the SSO form will open and ask for an email address to use for SSO login. GitKraken will then check the email and determine whether the email address belongs to a single IdP for SSO. When the email address is successfully identified, the user will be taken to that IdP to login.
## Troubleshooting / Error Messages
