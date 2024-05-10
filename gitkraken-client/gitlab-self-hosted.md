---

title: GitKraken Desktop GitLab Self-Managed Integration
description: Easily integrate GitKraken with you GitLab Self-Managed repository. Learn how to link GitKraken and GitLab Self-Managed by following these steps.
taxonomy:
    category: gitkraken-client

---

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/BhIX7fGSM8k?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

GitKraken allows you to connect to GitLab Self-Managed (CE or EE), which will help you find repos when cloning or adding your remotes.

**Benefits**

* Create repositories on GitLab Self-Managed server including .gitignore and license
* Automatically generate an SSH key pair and add it to GitLab Self-Managed
* Save authentication into profiles
* Clone from GitLab Self-Managed repo list
* Add remotes for GitLab Self-Managed repos
* Create and view Pull Requests
* Work with [GitLab Self-Managed Issues](/integrations/gitlab-self-managed-issues/)

***
## GitLab Self-Managed Authentication

<div class='callout callout'>
    <p>Note 📝 - GitKraken supports any version of GitLab Self-Managed released within one year.</p>
</div>

To authenticate with GitLab Self-Managed, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the _Integrations_ window, enter your _Host Domain_, then click the Generate a token on GitLab link.  Note the permissions that need to be assigned to the token on your GitLab Self-Managed server.

<img src="/wp-content/uploads/authentication-gitlab-self-managed.png" srcset="/wp-content/uploads/authentication-gitlab-self-managed@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you will log in with your GitLab Self-Managed credentials and generate an access token.

GitKraken needs the token to have `api` and `read_user` scope and we recommend leaving the Expiration field blank.

<img src="/wp-content/uploads/access-token-gitlab-self-managed.png" srcset="/wp-content/uploads/access-token-gitlab-self-managed@2x.png" class="img-bordered img-responsive center">

Copy your token to the clipboard as this is the only time you will see this token.  Paste the token into GitKraken and click on <button class='button button--success button--ui button--nolink'>Connect</button>.

<img src="/wp-content/uploads/authentication-connect-gitlab-self-managed.png" srcset="/wp-content/uploads/authentication-connect-gitlab-self-managed@2x.png" class="img-bordered img-responsive center">

## Generating an SSH Key for GitLab Self-Managed

<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitLab-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitLab Self-Managed account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitLab Self-Managed account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src="/wp-content/uploads/ssh-gitlab-self-managed.png" srcset="/wp-content/uploads/ssh-gitlab-self-managed@2x.png" class="img-bordered img-responsive center">

Click the <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitLab</button> button and watch the magic happen.

Alternatively add existing  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitLab</button> or an existing key pair through _Add existing SSH key_.

***

## Connecting to multiple GitLab Self-Managed accounts

GitKraken connects to one GitLab Self-Managed account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitLab Self-Managed accounts.
