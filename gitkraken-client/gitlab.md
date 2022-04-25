---

title: GitLab
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

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select _GitLab.com_ and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitLab</button> button.

<img src="/img/documentation/integrations/gitlab/gitlab-authentication.png" srcset="/img/documentation/integrations/gitlab/gitlab-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open your default web browser where you can click <button class='button button--success button--ui button--nolink'>Continue authorization</button> and then log in with your GitLab credentials.

<img src="/img/documentation/integrations/gitlab/authorize.png" srcset="/img/documentation/integrations/gitlab/authorize@2x.png 2x" class="img-responsive center img-bordered">

<img src="/img/documentation/integrations/gitlab/gitlab-sign-in.png" srcset="/img/documentation/integrations/gitlab/gitlab-sign-in@2x.png 2x" class="img-responsive center img-bordered">

You'll then see a success message below and the connection will be active in GitKraken 🎉

<img src="/img/documentation/integrations/gitlab/auth-success-gitlab.png" srcset="/img/documentation/integrations/gitlab/auth-success-gitlab@2x.png 2x" class="img-responsive center img-bordered">

### Generating an SSH Key for GitLab
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitLab-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitLab account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitLab account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

Click the magic <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitLab</button> button and watch what used to be 8 steps be complete in one.

Alternatively add a key from  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitLab</button> or an existing key pair through _Add existing SSH key_.

<img src="/img/documentation/integrations/gitlab/gitlab-ssh.png" srcset="/img/documentation/integrations/gitlab/gitlab-ssh@2x.png 2x" class="img-responsive center img-bordered">

***
## OAuth integration with GitLab
GitKraken's integration with GitLab provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/img/documentation/integrations/gitlab/clone.png" srcset="/img/documentation/integrations/gitlab/clone@2x.png" class="img-bordered img-responsive center">

Next, GitKraken presents a list of forks of the current repository when adding remotes:

<img src="/img/documentation/integrations/gitlab/remote.png" srcset="/img/documentation/integrations/gitlab/remote@2x.png" class="img-bordered img-responsive center">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple GitLab accounts

GitKraken connects to one GitLab account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitLab accounts.

***

## Training resources

Share these resources with your team to explain why collaborating with GitKraken is easier, and to get everyone up and running with GitLab and GitKraken quickly.


<div class='center'>
    <div class="flex-grid">
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/gitlab#how-to-gitlab-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/video-thumbs/gitlab-gitkraken.png'gitkraken-for-gitlab-cheat-sheet-2@2x.jpg 2x" alt='How to use GitLab with GitKraken video thumbnail' style="height: 150px; width: auto; max-width: none;">
                <p>How to use GitLab with GitKraken Video</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/gitlab#why-gitlab-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-gitlab-whitepaper.jpg' srcset="/img/downloads/gitkraken-gitlab-whitepaper@2x.jpg 2x" alt='GitKraken for GitLab Users cover' style="height: 150px; width: auto; max-width: none;">
                <p>GitLab White Paper<br />(PDF)</p>
            </a>
        </div>
        <div class="flex-item">
        	<a href='https://www.gitkraken.com/pdfs/gitkraken-git-gui-cheat-sheet' target='_blank' rel='noopener'>
        	    <img src='/img/downloads/gitkraken-cheat-sheet.png' srcset="/img/downloads/gitkraken-cheat-sheet@2x.png 2x" alt='GitKraken Cheat Sheet cover' style="height: 150px; width: auto; max-width: none;">
        	    <p>GitKraken Cheat Sheet<br />(PDF)</p>
        	</a>
        </div>
    </div>
    <div class="flex-grid">
        <div class="flex-item">
        	<a href='https://www.gitkraken.com/pdfs/why-gitkraken' target='_blank' rel='noopener'>
        	    <img src='/img/downloads/why-gitkraken.jpg' srcset="/img/downloads/why-gitkraken@2x.jpg 2x" alt='Why GitKraken cover' style="height: 150px; width: auto; max-width: none;">
        	    <p>Why GitKraken<br />(PDF)</p>
        	</a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/learn/git' target='_blank' rel='noopener'>
                <img src='/img/downloads/lgwgk.jpg' alt='Learning Git With GitKraken Image' style="height: 150px; width: auto; max-width: none;">
                <p>Learning Git Tutorial<br />Videos</p>
            </a>
        </div>
        <div class="flex-item"></div>
    </div>
</div>