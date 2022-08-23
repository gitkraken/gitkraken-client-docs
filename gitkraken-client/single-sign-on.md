---

title: Single Sign On (SSO)
description: How to enable and use Single Sign On (SSO)
taxonomy:
    category: gitkraken-client

---

GitKraken offers a Single Sign On (SSO) option as an easy way to sign in to your account. 

Once your organization has set up SSO with an Identity Provider (IdP), the Owner or an Admin on your GitKraken organization can link your organization to that identity provider. Then, any users associated with your IdP can login to GitKraken apps and services quickly. 🎉

<div class='callout callout--warning'>
    <p><strong>Note:</strong> You must have an active GitKraken Teams or Enterprise License to enable SSO</p>
</div>

## What is Single Sign On (SSO)?

The <a href='https://en.wikipedia.org/wiki/Single_sign-on' target='_blank'>Wikipedia</a> definition of SSO:

*“Single sign-on is an authentication scheme that allows a user to log in with a single ID to any of several related, yet independent, software systems. True single sign-on allows the user to log in once and access services without re-entering authentication factors.”*

<img src="/wp-content/uploads/sso-example-diagram.png" class="img-bordered img-responsive center">

The above diagram depicts what a typical SSO setup entails. Here is some relevant terminology:

**Directory Server:**  A Directory Server is an application that stores information about the “objects” that belong to an organization. An object is typically something like: printers, computers, shared folders, users, or groups. Some objects can contain other objects which then allows them to reflect hierarchical structures.  

Examples of Directory Server applications are:
* <a href='https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/ad-ds-getting-started' target='_blank'>Microsoft Active Directory</a> 
* <a href='https://www.oracle.com/security/identity-management/governance/' target='_blank'>Oracle Identity Governance (OIG) Suite</a> 
* <a href='https://jumpcloud.com/' target='_blank'>Jump Cloud</a> 

**Identity Provider:**  An identity provider (abbreviated IdP or IDP) is a system entity that creates, maintains, and manages identity information as well as provides authentication services to relying applications within a distributed network. An IdP provider stores 3 main components: Users, Groups, and Applications.

Examples of Identity Provider applications are:
* <a href='https://azure.microsoft.com/' target='_blank'>Azure Active Directory</a> 
* <a href='https://www.okta.com/' target='_blank'>Okta</a>
* <a href='https://cloud.google.com/identity-platform' target='_blank'>Google Identity Platform</a>

The Identity Providers provide services that allow third party applications to authenticate their users. The authentication mechanism they provide is called “Oauth”, which allows third party applications to authenticate users without accessing/storing their password. 

**Third party applications:** These are the applications that use IdP services to authenticate users. The end user is redirected to the IdP to instead login there. Then the Idp directs back to the 3rd party app to complete the login, confirming that the user is who they claim to be.

Examples of  third party apps:
* <a href='https://www.gitkraken.com/' target='_blank'>GitKraken</a> 
* <a href='https://slack.com/' target='_blank'>Slack</a> 
* <a href='https://www.atlassian.com/software/jira' target='_blank'>Jira</a> 

***
## SSO in GitKraken

GitKraken is a 3rd party application in this scenario. You (or an Owner/Admin) setup which IdP(s) you want to use and we will use them to log them in. If your organization has already set up SSO with an IdP and in GitKraken, simply [sign in](/gitkraken-client/single-sign-on/#logging-in-using-sso) and you are all set! 

If you need to set up SSO for your GitKraken Organization see [Setting up SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitkraken-organization)
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
* SSO can only be set up by the Owner or by an Admin of the organization. 

How to set up SSO:

1. <a href='https://app.gitkraken.com/' target='_blank'>Login</a> and navigate to the organization you want to enable SSO for.

2. On the left menu click on **SSO**.

<div class='callout callout--warning'>
    <p>If you do not see the SSO option, confirm that: 1. You are logged in as the Owner or an Admin for this organization 2. Your organization has either a Teams or Enterprise subscription</p>
</div>

3. Click the `Enable SSO` checkbox and you will be presented with some additional fields:

**Organization Domain Name:** The domain that is used for everyone who wants to use SSO to login. Each user must have a matching domain in their email address and each user must be defined in the IdP.

There is only one domain allowed per GitKraken organization, and it must be unique. If your domain is already in use you can <a href='https://www.gitkraken.com/git-client/contact-support' target='_blank'>contact support</a> for help.

**JIT, Enable Just In Time Provisioning:** This allows users in this domain to login with their email and be automatically provisioned a license. In order for a user to be automatically given a license:

* Just in time provisioning must be enabled (JIT option checked)☑.
* The user email must be part of the SSO domain on the IdP.
* There must be an available license on the GitKraken Organization.

When a user logs in for the first time using SSO, and all three of the above conditions are met, they will be automatically given a GitKraken license.

4. Click on <button class='button button--success button--ui button--nolink'>Save changes</button> to store the SSO configuration. Once this is completed you will see the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button appear.

5. Click the <button class='button button--success button--ui button--nolink'>Configure SSO Connection</button> button to set up the connection between your GitKraken Organization and the Identity Provider. You will now be able to configure the connection using [Metadata](/gitkraken-client/single-sign-on/#add-sso-connection-using-metadata).

### Add SSO Connection using Metadata

Click on <button class='button button--success button--ui button--nolink'>Add Using Metadata</button> and you will see the following fields:

+ **Identity Provider:** choose a [supported provider](/gitkraken-client/single-sign-on/#supported-identity-providers) from the drop-down.
+ **IdP Metadata URL /IdP Metadata:** depending on the  IdP we can use one or both of these options for setting up the SSO connection. 
+ **Don't enable this connection immediately** ✅ by default new connections are automatically enabled. This checkbox will create the connection but users will not be able to login using SSO with this IdP until it is enabled.

**Example 1:** setting up Otka

Okta is configured using a metadata file.
1. Access your Okta instance.
2. Navigate to the Application that you want to use. See our [Otka example](/gitkraken-client/single-sign-on/#otka) for an example of how to make one.
3. Click on “Sign on” and scroll down to SAML Signing Certificates:

<img src="/wp-content/uploads/sso-okta-certs.png" class="img-bordered img-responsive center">

4. Notice that there is just one Active. Click on Actions for the active certificate.

<img src="/wp-content/uploads/sso-okta-certs-actions.png" class="img-bordered img-responsive center">

5. Click on *Download certificate* and you will be prompted with an xml file.
6. Copy this file content and paste it into the *IdP metadata* field in the SSO Create Connection form.
7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” to not automatically enable this connection and prevent users from using it.

<img src="/wp-content/uploads/sso-okta-paste-metadata.png" class="img-bordered img-responsive center">

**Example 2:** setting up Azure Active Directory

Azure is configured using a metadata URL.
1. Access to your Azure account, and go to Active Directory -> *Enterprise Applications*.

<img src="/wp-content/uploads/sso-azure-applications.png" class="img-bordered img-responsive center">

2. Navigate to the application that you want to use. See our [Azure Active Directory example](/gitkraken-client/single-sign-on/#azure-active-directory) for an example of how to make one.
3. On the left menu select *Single Sign-on*.
4. Scroll down to the section: *SAML Signing Certificate*.

<img src="/wp-content/uploads/sso-azure-saml-cert.png" class="img-bordered img-responsive center">

5. Copy the *App Federation Metadata Url*.
6. Paste this URL into the *Idp metadata URL* field in SSO Create Connection:

<img src="/wp-content/uploads/sso-azure-paste-metadata-url.png" class="img-bordered img-responsive center">

7. Click on <button class='button button--success button--ui button--nolink'>Create Connection</button>. Optionally, you can check “Don’t enable this connection immediately” and choose to later enable it.

<div class='callout callout--none'>
    <p><strong>Note:</strong> “Just in time provisioning” is either turned on or turned off for all connections in the Organization.</p>
</div>

## Logging in using SSO

When logging into GitKraken Client, GitLens, <a href='https://account.gitkraken.com/account-info' target='_blank'>account.gitkraken.com</a> , or anywhere else to access your GitKraken account, you will see the `Sign In with SSO` option.

<img src="/wp-content/uploads/sso-sign-in.png" class="img-bordered img-responsive center">

After clicking **Sign in with SSO**, the SSO form will open and ask for an email address to use for SSO login. Enter your email address and GitKraken will determine which SSO option(s) are available and present them to you. Click an option and you will be sent to the IdP login page to complete the process.

## Example Identity Provider (IdP) setup instructions

<div class='callout callout--warning'>
    <p><strong>Note:</strong> These are example instructions to help you with Identity Provider setup. In most cases all you will need from us is the callback URL: https://api.gitkraken.com/oauth/sso/callback. If you need assistance please contact your IdP administrator or consult the IdP documentation for help.</p>
</div>

### G Suite

How to Create SAML Application in G Suite:

1. Go to https://admin.google.com/ 

2. Click on *Apps* and then *Web and mobile apps*.

<img src="/wp-content/uploads/sso-example-idp-1.jpg" class="img-bordered img-responsive center">

3. Click on *Add app*. 

<img src="/wp-content/uploads/sso-example-idp-2.jpg" class="img-bordered img-responsive center">

4. Click *Add custom SAML app*.

<img src="/wp-content/uploads/sso-example-idp-3.jpg" class="img-bordered img-responsive center">

5. Type in your app name (such as GitKraken SSO).

<img src="/wp-content/uploads/sso-example-idp-4.jpg" class="img-bordered img-responsive center">

6. Copy your *SSO URL* and *Certificate*.

<img src="/wp-content/uploads/sso-example-idp-5.jpg" class="img-bordered img-responsive center">

7. Enter the callback URL `https://api.gitkraken.com/oauth/sso/callback` for *ACS URL* and *Entity ID*.

<img src="/wp-content/uploads/sso-example-idp-6.jpg" class="img-bordered img-responsive center">

8. Add desired attributes and click on *Finish*.

<img src="/wp-content/uploads/sso-example-idp-7.jpg" class="img-bordered img-responsive center">

9. Click on *TEST SAML LOGIN*.

<img src="/wp-content/uploads/sso-example-idp-8.jpg" class="img-bordered img-responsive center">

10. Click on *ALLOW ACCESS*.

<img src="/wp-content/uploads/sso-example-idp-9.jpg" class="img-bordered img-responsive center">

11. Select *ON for everyone* and save.

<img src="/wp-content/uploads/sso-example-idp-10.jpg" class="img-bordered img-responsive center">

Now you are all set to [setup your SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitKraken-organization)

### Azure Active Directory

How to create SAML application in Azure Active Directory:

1. In a browser, go to Azure login portal.
2. Enter your azure credentials and login.
3. Go to *Azure Active Directory* from search bar.
4. In the left menu click on *Enterprise applications*.

<img src="/wp-content/uploads/sso-azure-1.png" class="img-bordered img-responsive center">

5. Click on *New application* from the top of the page.

<img src="/wp-content/uploads/sso-azure-2.png" class="img-bordered img-responsive center">

6. Select *Create your own application*. 

<img src="/wp-content/uploads/sso-azure-3.png" class="img-bordered img-responsive center">

7. Give your application name (such as "GitKraken SSO") and select "Integrate any other application you don't find in the gallery (Non-gallery)".

<img src="/wp-content/uploads/sso-azure-4.png" class="img-bordered img-responsive center">

8. Select *Single sign-on* from the left sidebar and then choose *SAML*.

<img src="/wp-content/uploads/sso-azure-5.png" class="img-bordered img-responsive center">

9. Click the edit icon in the top right corner to configure SAML.

<img src="/wp-content/uploads/sso-azure-6.png" class="img-bordered img-responsive center">

10.  Input the *Entity ID* URI and *Reply URL*. Both of these should direct to `https://api.gitkraken.com/oauth/sso/callback` for GitKraken SSO. 

<img src="/wp-content/uploads/sso-azure-7.png" class="img-bordered img-responsive center">

Now you are all set to [setup your SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitKraken-organization)
### Otka

How to Create SAML Application in Okta:

1. In a browser go to the Okta login page.
2. Enter your Otka credentials and login.
3. Go to admin dashboard and select *Applications* in navigation bar.

<img src="/wp-content/uploads/sso-otka-1.png" class="img-bordered img-responsive center">

4. Click on *Add Application*.  
5. Select *Create New App*. 

<img src="/wp-content/uploads/sso-otka-2.png" class="img-bordered img-responsive center">

6. Select *SAML 2.0* as a Sign on Method and click to next button.

<img src="/wp-content/uploads/sso-otka-3.png" class="img-bordered img-responsive center">

7. Enter a name of application (such as "GitKraken SSO").

<img src="/wp-content/uploads/sso-otka-4.png" class="img-bordered img-responsive center">

8. Configure SAML Integration. The *Single sign on URL* and *Audience URI* fields should direct to `https://api.gitkraken.com/oauth/sso/callback`.

<img src="/wp-content/uploads/sso-otka-5.png" class="img-bordered img-responsive center">

Step 9: Scroll down to the attribute statement and fill in the optional fields.

<img src="/wp-content/uploads/sso-otka-6.png" class="img-bordered img-responsive center">

Step 10: Select “I am an Okta customer adding an internal app” from option menu and then click to finish.

<img src="/wp-content/uploads/sso-otka-7.png" class="img-bordered img-responsive center">

Now you are all set to [setup your SSO on a GitKraken Organization](/gitkraken-client/single-sign-on/#setting-up-sso-on-a-gitKraken-organization)

### Ping Identity

How to Create SAML Application in Ping Identity

1. Go to https://www.pingidentity.com/en/account/sign-on.html

2. Create an account or sign in your existing one.

3. Go to the home page and click on *Add Environment*.

<img src="/wp-content/uploads/sso-pingidentity-3.png" class="img-bordered img-responsive center">

4. Select the appropriate solution based on your need (in this guide, we use *Customer solution*) and click *Next*.

<img src="/wp-content/uploads/sso-pingidentity-4.png" class="img-bordered img-responsive center">

5.	Select *PingOne SSO*, then click *Next*.

<img src="/wp-content/uploads/sso-pingidentity-5.png" class="img-bordered img-responsive center">

6.	Type in your environment name (in *TRIAL ENVIRONMENT NAME*), then click “Finish”. Now your environment is created. Go ahead and click on it.

<img src="/wp-content/uploads/sso-pingidentity-6.png" class="img-bordered img-responsive center">
<img src="/wp-content/uploads/sso-pingidentity-6-2.png" class="img-bordered img-responsive center">

7.	Select *Identities* to add some users. Once you are done adding them, go ahead and click on *Groups*, then click on the plus button to add a group. (Make sure to add users with their email addresses).

<img src="/wp-content/uploads/sso-pingidentity-7.png" class="img-bordered img-responsive center">
<img src="/wp-content/uploads/sso-pingidentity-7-2.png" class="img-bordered img-responsive center">

8.	Select *Groups*, then click on the plus button to add a group. Once you have that, you can add the users to your group.

<img src="/wp-content/uploads/sso-pingidentity-8.png" class="img-bordered img-responsive center">

9.	Select *Connections*.

<img src="/wp-content/uploads/sso-pingidentity-9.png" class="img-bordered img-responsive center">

10.	Click on the plus button.

<img src="/wp-content/uploads/sso-pingidentity-10.png" class="img-bordered img-responsive center">

11.	Enter a name for your application, then select *SAML Application*. Next click on the *Configure* button which appears once you select your application type.

<img src="/wp-content/uploads/sso-pingidentity-11.png" class="img-bordered img-responsive center">

12.	Select *Manually Enter*. Type in the URL for *ACS URLs* and *Entity ID*, then click on *Save*.

<img src="/wp-content/uploads/sso-pingidentity-12.png" class="img-bordered img-responsive center">

13.	Click on the toggle button so the users would have access to your application.

<img src="/wp-content/uploads/sso-pingidentity-13.png" class="img-bordered img-responsive center">

14.	Click on *Attributes* then add email as your new attribute.

<img src="/wp-content/uploads/sso-pingidentity-14.png" class="img-bordered img-responsive center">
<img src="/wp-content/uploads/sso-pingidentity-14-2.png" class="img-bordered img-responsive center">

15. Time to add the group we created.

<img src="/wp-content/uploads/sso-pingidentity-15.png" class="img-bordered img-responsive center">

16.	Click on the button below.

<img src="/wp-content/uploads/sso-pingidentity-16.png" class="img-bordered img-responsive center">

17.	Click on the plus icon to add the group, then click on *Save*.

<img src="/wp-content/uploads/sso-pingidentity-17.png" class="img-bordered img-responsive center">
<img src="/wp-content/uploads/sso-pingidentity-17-2.png" class="img-bordered img-responsive center">

18.	Go to the *Configuration* tab to copy your *IDP Metadata URL* and download your metadata (*Download Metadata* button).

<img src="/wp-content/uploads/sso-pingidentity-18.png" class="img-bordered img-responsive center">

19.	Go to your organization and click on *SSO* then click on *Enable SSO*. Type in your domain in *Organization Domain Name* with *.com* . Then click on *Configure SSO Connection*.

<img src="/wp-content/uploads/sso-pingidentity-19.png" class="img-bordered img-responsive center">

20.	Click on *Add Using Metadata* and type in a *Connection name* and from the *Identity Provider* select *Ping Identity*. Then use the *IDP Metadata URL* and *Metadata* from step 18 for *IdP Metadata URL* and *IdP Metadata*. Click on *Create Connection*

<img src="/wp-content/uploads/sso-pingidentity-20.png" class="img-bordered img-responsive center">

21.	Now the users who were added in step 7 can *Sign in with SSO*.

