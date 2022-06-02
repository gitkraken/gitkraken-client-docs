---

title: GitKraken Client GitHub Enterprise Integration
description: Easily integrate GitKraken with you GitHub Enterprise repository. Learn how to link GitKraken and GitHub Enterprise by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken allows you to connect to GitHub Enterprise, which will help you find repos when cloning or adding your remotes.

**Benefits**

* Create repositories on GitHub Enterprise account including .gitignore and license
* Automatically generate an SSH key pair and add it to GitHub Enterprise
* [Fork repositories](/working-with-repositories/fork/) from GitKraken
* Save authentication into profiles
* Clone from GitHub Enterprise repo list
* Add remotes for GitHub Enterprise repos
* Create and view Pull Requests

***
## GitHub Enterprise Authentication

<div class='callout callout'>
    <p>Note 📝 - GitKraken supports any version of GitHub Enterprise released within one year.</p>
</div>

To authenticate with GitHub Enterprise, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, enter your _Host Domain_ then click the Generate an access token on _your URL_ link.

<img src="/wp-content/uploads/authentication-github-enterprise.png" srcset="/wp-content/uploads/authentication-github-enterprise@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you next log in with your GitHub Enterprise credentials and generate an access token.

<img src='/wp-content/uploads/accesstoken-github-enterprise.png' class='center img-bordered'>

Copy your token to the clipboard as this is the only time you will see this token.  Paste the token into GitKraken and click on <button class='button button--success button--ui button--nolink'>Connect</button>.

<img src="/wp-content/uploads/authentication-connect-github-enterprise.png" srcset="/wp-content/uploads/authentication-connect-github-enterprise.png" class="img-bordered img-responsive center">

### Generating an SSH Key for GitHub Enterprise
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitHub-specific SSH key, or enable your local SSH Agent.</p>
</div>
Once your GitHub Enterprise account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitHub Enterprise account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src='/wp-content/uploads/ssh-github-enterprise.png' srcset='/wp-content/uploads/ssh-github-enterprise@2x.png' class='center img-responsive img-bordered'>

Click the <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitHub Enterprise</button> button and watch the magic happen.

Alternatively add existing  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitHub Enterprise</button> or an existing key pair through _Add existing SSH key_.

***

## Connecting to multiple GitHub Enterprise accounts

GitKraken connects to one GitHub Enterprise account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitHub Enterprise accounts.

***
