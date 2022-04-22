---

title: GitLab Self-Managed
description: Easily integrate GitKraken with you GitLab Self-Managed repository. Learn how to link GitKraken and GitLab Self-Managed by following these steps.
taxonomy:
    category: gitkraken-client

---

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

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the _Integrations_ window, enter your _Host Domain_, then click the Generate a token on GitLab link.  Note the permissions that need to be assigned to the token on your GitLab Self-Managed server.

<img src="/img/documentation/integrations/gitlab-self-hosted/authentication.png" srcset="/img/documentation/integrations/gitlab-self-hosted/authentication@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you will log in with your GitLab Self-Managed credentials and generate an access token.  

GitKraken needs the token to have `api` and `read_user` scope and we recommend leaving the Expiration field blank.

<img src="/img/documentation/integrations/gitlab-self-hosted/access-token.png" srcset="/img/documentation/integrations/gitlab-self-hosted/access-token@2x.png" class="img-bordered img-responsive center">

Copy your token to the clipboard as this is the only time you will see this token.  Paste the token into GitKraken and click on <button class='button button--success button--ui button--nolink'>Connect</button>.

<img src="/img/documentation/integrations/gitlab-self-hosted/authentication-connect.png" srcset="/img/documentation/integrations/gitlab-self-hosted/authentication-connect@2x.png" class="img-bordered img-responsive center">

## Generating an SSH Key for GitLab Self-Managed

<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitLab-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitLab Self-Managed account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitLab Self-Managed account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src="/img/documentation/integrations/gitlab-self-hosted/ssh.png" srcset="/img/documentation/integrations/gitlab-self-hosted/ssh@2x.png" class="img-bordered img-responsive center">

Click the <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitLab</button> button and watch the magic happen.

Alternatively add existing  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitLab</button> or an existing key pair through _Add existing SSH key_.

***

## Connecting to multiple GitLab Self-Managed accounts

GitKraken connects to one GitLab Self-Managed account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitLab Self-Managed accounts.

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