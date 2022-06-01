---

title: GitKraken Client Bitbucket Self-Hosted Integration
description: Integrate GitKraken Client with your Bitbucket Server repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken Client allows you to authenticate with Bitbucket Server, which will help you find repos on Bitbucket Server when cloning or adding your remotes.

**Benefits**

* Create repositories on Bitbucket Server including .gitignore and license
* Easily generate an SSH key pair and copy to clipboard to add to Bitbucket Server
* Save authentication into profiles
* Clone from Bitbucket Server repo list
* Add remotes for Bitbucket Server repos
* Create and view Pull Requests

***

## Connecting to Bitbucket Server

<div class='callout callout'>
    <p>Note 📝 - GitKraken Client supports any version of Bitbucket Server released within one year.</p>
</div>

To authenticate with Bitbucket Server, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select **Bitbucket Server**. Enter your host domain URL and then click the Generate a token on Bitbucket Server button. Note the permissions that need to be assigned to the token on your Bitbucket Self-Hosted server.

<img src="/wp-content/uploads/preferences-authentication-bitbucket-server.png" srcset="/wp-content/uploads/preferences-authentication-bitbucket-server@2x.png 2x" class="img-responsive center img-bordered">

This opens a web browser where you will log in with your Bitbucket Server credentials and create an access token.

<img src='/wp-content/uploads/BitbucketServerPAT.png' class="img-responsive center img-bordered">

Copy the token and paste it into GitKraken Client, then click the <button class='button button--success button--ui button--nolink'>Connect</span></button> button.

<img src="/wp-content/uploads/bitbucket-server-connected.png" srcset="/wp-content/uploads/bitbucket-server-connected@2x.png 2x" class="img-responsive center img-bordered">

***
## Generating SSH keys for Bitbucket Server.
<div class='callout callout'>
    <p>Note 📝 - GitKraken Client uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a BitBucket-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your Bitbucket Server account has been connected to your GitKraken Client, you may then generate an SSH key and add it to your Bitbucket Server account from <em class='context-menu'>Preferences     <i class='fa fa-caret-right'></i>    Integrations</em>

Click <button class='button button--success button--ui button--nolink'>Generate SSH key and copy to clipboard</span></button> and follow the toast prompt to add the key to your Bitbucket Server account. If you miss the toast pop-up or need to copy the public key later, you can use the link as well.

<img src='/wp-content/uploads/bitbucket-server-SSHkey.png' class="img-responsive center img-bordered">

In your Bitbucket Server SSH keys page, click <button class='button button--primary button--ui button--nolink'>Add Key</span></button>.

<img src='/wp-content/uploads/bitbucket-server-add-key.png' class="img-responsive center img-bordered">

Paste your key and click <button class='button button--primary button--ui button--nolink'>Add Key</span></button>.

<img src="/wp-content/uploads/bitbucket-server-SSHkey-add.png" srcset="/wp-content/uploads/bitbucket-server-SSHkey-add@2x.png 2x" class="img-responsive center img-bordered">

***
## OAuth integration with Bitbucket Server
GitKraken's integration with Bitbucket Server provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/wp-content/uploads/bitbucket-server-clone-menu.png" srcset="/wp-content/uploads/bitbucket-server-clone-menu@2x.png 2x" class="img-responsive center img-bordered">

Next, GitKraken Client presents a list of forks of the current repository when adding remotes:

<img src="/wp-content/uploads/-server-add-remote.png" class="img-responsive center img-bordered">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple Bitbucket Server accounts

GitKraken connects to one Bitbucket Server account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated Bitbucket Server accounts.

***
