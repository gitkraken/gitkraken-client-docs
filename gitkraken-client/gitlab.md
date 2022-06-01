---

title: GitKraken Client GitLab Integration
description: Integrate GitKraken with your GitLab repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken allows you to connect to [GitLab](https://gitlab.com), which will help you find repos on GitLab when cloning.

**Benefits**

* Create repositories on GitLab account including .gitignore and license
* Automatically generate an SSH key pair and add it to GitLab
* Clone from GitLab repo list
* Identify GitLab repos with remote avatars on graph
* Add remotes for GitLab repos
* Create and view Pull Requests
* Work with [GitLab Issues](/integrations/gitlab-issues/)


***

## GitLab Authentication

To authenticate with GitLab, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select _GitLab.com_ and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitLab</button> button.

<img src="/wp-content/uploads/gitlab-authentication.png" srcset="/wp-content/uploads/gitlab-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open your default web browser where you can click <button class='button button--success button--ui button--nolink'>Continue authorization</button> and then log in with your GitLab credentials.

<img src="/wp-content/uploads/authorize-gitlab.png" srcset="/wp-content/uploads/authorize-gitlab@2x.png 2x" class="img-responsive center img-bordered">

<img src="/wp-content/uploads/gitlab-sign-in.png" srcset="/wp-content/uploads/gitlab-sign-in@2x.png 2x" class="img-responsive center img-bordered">

You'll then see a success message below and the connection will be active in GitKraken 🎉

<img src="/wp-content/uploads/auth-success-gitlab.png" srcset="/wp-content/uploads/auth-success-gitlab@2x.png 2x" class="img-responsive center img-bordered">

### Generating an SSH Key for GitLab
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitLab-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitLab account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitLab account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

Click the magic <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitLab</button> button and watch what used to be 8 steps be complete in one.

Alternatively add a key from  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitLab</button> or an existing key pair through _Add existing SSH key_.

<img src="/wp-content/uploads/gitlab-ssh.png" srcset="/wp-content/uploads/gitlab-ssh@2x.png 2x" class="img-responsive center img-bordered">

***
## OAuth integration with GitLab
GitKraken's integration with GitLab provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/wp-content/uploads/clone-gitlab.png" srcset="/wp-content/uploads/clone-gitlab@2x.png" class="img-bordered img-responsive center">

Next, GitKraken presents a list of forks of the current repository when adding remotes:

<img src="/wp-content/uploads/remote-gitlab.png" srcset="/wp-content/uploads/remote-gitlab@2x.png" class="img-bordered img-responsive center">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple GitLab accounts

GitKraken connects to one GitLab account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitLab accounts.

***
