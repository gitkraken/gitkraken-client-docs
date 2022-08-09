---

title: Single Sign On (SSO)
description: How to enable and use Single Sign On (SSO)
taxonomy:
    category: gitkraken-client

---

GitKraken offers a Single Sign On (SSO) option as an easy way to sign in to your account. 

Once your organization has setup SSO with an Identity Provider (IdP), the Owner or an Admin on your GitKraken organization can link your orgazation to that identity provider. Then, any users associated with your IdP can login to GitKraken apps and services quickly. 🎉

<div class='callout callout--warning'>
    <p><strong>Note:</strong> You must have an active GitKraken Teams or Enterprise License to enable SSO</p>
</div>

## What is Single Sign On (SSO)?

The <a href='https://en.wikipedia.org/wiki/Single_sign-on' target='_blank'>Wikipedia</a> definition of SSO:

*“Single sign-on is an authentication scheme that allows a user to log in with a single ID to any of several related, yet independent, software systems. True single sign-on allows the user to log in once and access services without re-entering authentication factors.”*

<img src="/wp-content/uploads/sso-example-diagram.png" class="img-bordered img-responsive center">

The above diagram depicts what a typical SSO setup entails. These are the applications or actors involved in the setup:

**Directory Server:**  A Directory Server is an application that stores information about the “objects” that belong to an organization. An object can be: printers, computers, shared folders, users, groups (a group is just a group of users). Some objects can contain other objects, which then allows them to reflect hierarchical structures.  

Examples of Directory Server applications are:
* <a href='https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/ad-ds-getting-started' target='_blank'>Microsoft Active Directory</a> 
* <a href='https://www.oracle.com/security/identity-management/governance/' target='_blank'>Oracle Identity Governance (OIG) Suite</a> 
* <a href='https://jumpcloud.com/' target='_blank'>Jump Cloud</a> 

**Identity Provider:**  An identity provider (abbreviated IdP or IDP) is a system entity that creates, maintains, and manages identity information for principals and also provides authentication services to relying applications within a federation or distributed network. An IdP provider stores 3 main components: Users, Groups, and Applications.

Examples of Identity Provider applications are:
* <a href='https://azure.microsoft.com/' target='_blank'>Azure Active Directory</a> 
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>Google Identity Platform</a>

The Identity Providers provide services that allow third party applications to authenticate their users. 
The authentication mechanism they provide is called “Oauth”, which allows third party applications to authenticate users without accessing/storing their password. 

**Third party applications:** These are the applications that use IdP services to authenticate users. The end user is redirected to the IdP to instead login there. Then the Idp directs back to the 3rd party app to complete the login, confirming that the user is who they claim to be.

Examples of  third party apps:
* <a href='https://www.gitkraken.com/' target='_blank'>GitKraken</a> 
* <a href='https://slack.com/' target='_blank'>Slack</a> 
* <a href='https://www.atlassian.com/software/jira' target='_blank'>Jira</a> 

***
## SSO in GitKraken

GitKraken is a 3rd party application in this scenario - you setup which IdP(s) you want to use and we will use them to log them in. If your organization has already setup SSO with an IdP and in GitKraken, simply [sign in](/gitkraken-client/single-sign-on/#logging-in-using-sso) and you are all set! 

If you need to setup SSO for your GitKraken Organization see [Setting up SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitkraken-organization)
### Supported Identity Providers

GitKraken may initiate an Oauth authentication flow with the following supported Identity Providers (IdPs):

* <a href='https://azure.microsoft.com/' target='_blank'>Azure Active Directory</a> 
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>Google Identity Platform (G Suite)</a>

<div class='callout callout--warning'>
    <p><strong>Note:</strong> Your IdP(s) will first need to be configured before setting up the connection in GitKraken.</p>
</div>

While we do not assist in setting up with an identity provider, check out this [example IdP setup](/gitkraken-client/single-sign-on/#example-idp-setup-instructions) to see what this portion typically looks like.

### License Requirements

Single Sign On is available as part of the <a href='https://www.gitkraken.com/git-client/pricing' target='_blank'>teams and enterprise plans</a>. 

### Setting up SSO on a GitKraken Organization

First, some quick notes:

* SSO is set up at the Organization level. Each organization can have 0,1, or many identity providers connected simultaneously.
* SSO can only be setup by the Owner or by an Admin of the organization. 

How to set up SSO:

1. <a href='https://app.gitkraken.com/' target='_blank'>Login</a> and navigate to the organization you want to enable SSO for.

2. On the left menu click on **SSO**.

<div class='callout callout--warning'>
    <p>If you do not see the SSO option, confirm that: you are logged in as the Owner or an Admin for this organization, your organization has either a Teams or Enterprise subscription</p>
</div>

3. Click the `Enable SSO` checkbox and you will be presented with some additional fields:

**Organization Domain Name:** The domain that is used for everyone who wants to use SSO to login. Each user must have a matching domain in their email address and each user must be defined in the IdP.

There is only one domain allowed per GitKraken organization, and it must be unique. If your domain is already in use you can <a href='https://www.gitkraken.com/git-client/contact-support' target='_blank'>contact support</a> for help.

**JIT, Enable Just In Time Provisioning:** This allows users in this domain to login with their email and be automatically provisioned a license. In order for a user to be automatically given a license:

* Just in time provisioning must be enabled (JIT option checked)☑ .
* The user email must be part of the SSO domain on the IdP.
* There must be an availible licence on the GitKraken Organization.

If this field is checked, when a user logs in into the Accounts Site for the first time, without having a license, using SSO with an email which domains belong to a gitKraken org. If there is any available license in the gitkraken org he/she will be automatically given one. 

Click on <button class='button button--success button--ui button--nolink'>Save changes</button>, for storing the SSO configuration. Once that is completed, you will see the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button appear.

4. Click the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button to setup the connection between your GitKraken Organization and the Identity Provider.

Here you will see a list of all of the currently setup SSO connections. 

### Add SSO Connection using Metadata

Click on <button class='button button--success button--ui button--nolink'>Add Using Metadata</button> and you will see the following fields:

+ **Identity Provider:** choose a [supported provider](/gitkraken-client/single-sign-on/#supported-identity-providers) from the drop-down.
+ **IdP Metadata URL /IdP Metadata:** depending on the  IdP we can use one or both of thse options for setting up the SSO connection. 
+ **Don't enable this conenction immediately** ✅ by default new connections are automatically enabled. This checkbox will create the connection but users will not be able to login using SSO with this IdP until it is enabled.

Example 1: setting up Otka

Okta is configured by using a metadata file.
1. Access your Okta instance.
2. Navigate to the Application that you want to use.
3. Click on “Sign on” and scroll down to SAML Signing Certificates:

<img src="/wp-content/uploads/sso-okta-certs.png" class="img-bordered img-responsive center">

4. Notice that there is just one Active. Click on Actions for the active certificate.

<img src="/wp-content/uploads/sso-okta-certs-actions.png" class="img-bordered img-responsive center">

5. Click on *Download certificate* and you will be prompted with an xml file.
6. Copy this file content and paste it into the *IdP metadata* field in the SSO Create Connection form.
7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” to not automatically enable this connection and prevent users from using it.

<img src="/wp-content/uploads/sso-okta-paste-metadata.png" class="img-bordered img-responsive center">

Example 2: setting up Azure

1. Access to your Azure account, and go to Active Directory -> Enterprise Applications.

<img src="/wp-content/uploads/sso-azure-applications.png" class="img-bordered img-responsive center">

2. Navigate to the application that you want to use.
3. On the left menu select “Single Sign-on”.
4. Scroll down to the section: “SAML Signing Certificate”.

<img src="/wp-content/uploads/sso-azure-saml-cert.png" class="img-bordered img-responsive center">

5. Copy the “App Federation Metadata Url”.
6. Paste this URL into the “Idp metadata URL” field in SSO Create Connection:

<img src="/wp-content/uploads/sso-azure-paste-metadata-url.png" class="img-bordered img-responsive center">

7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” to not automatically enable this connection and prevent users from using it.


<div class='callout callout--none'>
    <p><strong>Note:</strong> “Just in time provisioning” is either turned on or turned off for all connections in the Organization.</p>
</div>

## Logging in using SSO

When logging into GitKraken Client, GitLens, <a href='https://account.gitkraken.com/account-info' target='_blank'>account.gitkraken.com</a> , or anywhere else to access your GitKraken account, you will see the `Sign In with SSO` option.

<img src="/wp-content/uploads/sso-sign-in.png" class="img-bordered img-responsive center">

After clicking “Sign in with SSO”, the SSO form will open and ask for an email address to use for SSO login. Enter your email address and GitKraken will determine which SSO Option(s) are availible and present them to you. Click an option and you will be sent to the IdP to complete the login process.

## Example Identity Provider (IdP) setup instructions

<div class='callout callout--warning'>
    <p><strong>Note:</strong> These are example instructions to help you with Identity Provider setup. For assistance please contact your IdP administrator or consult the IdP documentation for help.</p>
</div>

How to Create SAML Application in G Suite:

1. Go to https://admin.google.com/ 

2. Click on “Apps” and then “Web and mobile apps”

<img src="/wp-content/uploads/sso-example-idp-1.jpg" class="img-bordered img-responsive center">

3. Click on “Add app” 

<img src="/wp-content/uploads/sso-example-idp-2.jpg" class="img-bordered img-responsive center">

4. Click “Add custom SAML app”

<img src="/wp-content/uploads/sso-example-idp-3.jpg" class="img-bordered img-responsive center">

5. Type in your app name

<img src="/wp-content/uploads/sso-example-idp-4.jpg" class="img-bordered img-responsive center">

6. Copy your “SSO URL” and “Certificate”

<img src="/wp-content/uploads/sso-example-idp-5.jpg" class="img-bordered img-responsive center">

7. Type in your “https://baseURL/oauth/sso/callback” for “ACS URL” and “Entity ID”

<img src="/wp-content/uploads/sso-example-idp-6.jpg" class="img-bordered img-responsive center">

8. Add desired attributes and click on “Finish”

<img src="/wp-content/uploads/sso-example-idp-7.jpg" class="img-bordered img-responsive center">

9. Click on “TEST SAML LOGIN”

<img src="/wp-content/uploads/sso-example-idp-8.jpg" class="img-bordered img-responsive center">

10. Click on “ALLOW ACCESS”

<img src="/wp-content/uploads/sso-example-idp-9.jpg" class="img-bordered img-responsive center">

11. Select “ON for everyone” and save 

<img src="/wp-content/uploads/sso-example-idp-10.jpg" class="img-bordered img-responsive center">

Now you are all set to [setup your your SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitKraken-organization)