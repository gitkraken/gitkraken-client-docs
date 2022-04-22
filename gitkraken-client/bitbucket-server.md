---

title: Bitbucket Self-Hosted
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

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select **Bitbucket Server**. Enter your host domain URL and then click the Generate a token on Bitbucket Server button. Note the permissions that need to be assigned to the token on your Bitbucket Self-Hosted server.

<img src="/img/documentation/integrations/bitbucket-server/preferences-authentication-bitbucket-server.png" srcset="/img/documentation/integrations/bitbucket-server/preferences-authentication-bitbucket-server@2x.png 2x" class="img-responsive center img-bordered">

This opens a web browser where you will log in with your Bitbucket Server credentials and create an access token.

<img src='/img/documentation/integrations/bitbucket-server/BitbucketServerPAT.png' class="img-responsive center img-bordered">

Copy the token and paste it into GitKraken Client, then click the <button class='button button--success button--ui button--nolink'>Connect</span></button> button.

<img src="/img/documentation/integrations/bitbucket-server/bitbucket-server-connected.png" srcset="/img/documentation/integrations/bitbucket-server/bitbucket-server-connected@2x.png 2x" class="img-responsive center img-bordered">

***
## Generating SSH keys for Bitbucket Server.
<div class='callout callout'>
    <p>Note 📝 - GitKraken Client uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a BitBucket-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your Bitbucket Server account has been connected to your GitKraken Client, you may then generate an SSH key and add it to your Bitbucket Server account from <em class='context-menu'>Preferences     <i class='fa fa-caret-right'></i>    Integrations</em>    

Click <button class='button button--success button--ui button--nolink'>Generate SSH key and copy to clipboard</span></button> and follow the toast prompt to add the key to your Bitbucket Server account. If you miss the toast pop-up or need to copy the public key later, you can use the link as well.

<img src='/img/documentation/integrations/bitbucket-server/bitbucket-server-SSHkey.png' class="img-responsive center img-bordered">

In your Bitbucket Server SSH keys page, click <button class='button button--primary button--ui button--nolink'>Add Key</span></button>. 

<img src='/img/documentation/integrations/bitbucket-server/bitbucket-server-add-key.png' class="img-responsive center img-bordered">

Paste your key and click <button class='button button--primary button--ui button--nolink'>Add Key</span></button>. 

<img src="/img/documentation/integrations/bitbucket-server/bitbucket-server-SSHkey-add.png" srcset="/img/documentation/integrations/bitbucket-server/bitbucket-server-SSHkey-add@2x.png 2x" class="img-responsive center img-bordered">

***
## OAuth integration with Bitbucket Server
GitKraken's integration with Bitbucket Server provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/img/documentation/integrations/bitbucket-server/bitbucket-server-clone-menu.png" srcset="/img/documentation/integrations/bitbucket-server/bitbucket-server-clone-menu@2x.png 2x" class="img-responsive center img-bordered">

Next, GitKraken Client presents a list of forks of the current repository when adding remotes:

<img src="/img/documentation/integrations/bitbucket-server/bitbucket-server-add-remote.png" class="img-responsive center img-bordered">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple Bitbucket Server accounts

GitKraken connects to one Bitbucket Server account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated Bitbucket Server accounts.

***

## Training resources

Share these resources with your team to explain why collaborating with GitKraken Client is easier, and to get everyone up and running with Bitbucket and GitKraken quickly.


<div class='center'>
    <div class="flex-grid">
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/bitbucket#how-to-bitbucket-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/video-thumbs/bitbucket-gitkraken.png'gitkraken-for-bitbucket-cheat-sheet-2@2x.jpg 2x" alt='How to use Bitbucket with GitKraken video thumbnail' style="height: 150px; width: auto; max-width: none;">
                <p>How to use Bitbucket with GitKraken Video</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/bitbucket#why-bitbucket-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-bitbucket-whitepaper.jpg' srcset="/img/downloads/gitkraken-bitbucket-whitepaper@2x.jpg 2x" alt='GitKraken for Bitbucket Users cover' style="height: 150px; width: auto; max-width: none;">
                <p>Bitbucket White Paper<br />(PDF)</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/pdfs/gitkraken-git-gui-cheat-sheet' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-cheat-sheet.png' srcset="/img/downloads/gitkraken-cheat-sheet@2x.png 2x" alt='GitKraken Cheat Sheet cover' style="height: 150px; width: auto; max-width: none;">
                <p>GitKraken Client Cheat Sheet<br />(PDF)</p>
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