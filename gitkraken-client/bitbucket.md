---

title: Bitbucket
description: Integrate GitKraken with your Bitbucket repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken Client allows you to authenticate with Bitbucket, which will help you find repos on Bitbucket when cloning or adding your remotes.

**Benefits**

* Create repositories on Bitbucket account including .gitignore and license
* Easily generate an SSH key pair and copy to clipboard to add to Bitbucket
* Save authentication into profiles
* Clone from Bitbucket repo list
* Add remotes for Bitbucket repos
* Create and view Pull Requests

<div class='embed-container embed-container--16-9'>
    <iframe width='560' height='315' src='https://www.youtube.com/embed/sQ4ouJpAeR8?rel=0&vq=hd1080' frameborder='0' allowfullscreen></iframe>
</div>

***

## Connecting to Bitbucket

To authenticate with Bitbucket, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select Bitbucket.org and then hit the <button class='button button--success button--ui button--nolink'>Connect to Bitbucket</span></button> button.

<img src="/img/documentation/integrations/bitbucket/preferences-authentication.png" srcset="/img/documentation/integrations/bitbucket/preferences-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open a web browser where you will need to log in with your Bitbucket credentials to allow GitKraken access.

Upon login, you'll see a success message below and the connection will be active in GitKraken Client.

<img src="/img/documentation/integrations/bitbucket/bitbucket-success.png" srcset="/img/documentation/integrations/bitbucket/bitbucket-success@2x.png 2x" class="img-responsive center img-bordered">

***
## Generating SSH keys for Bitbucket.
<div class='callout callout'>
    <p>Note 📝 - GitKraken Client uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a BitBucket-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your Bitbucket account has been connected to GitKraken, you may then generate an SSH key and add it to your Bitbucket account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>    Integrations</i></kbd>

Click <button class='button button--success button--ui button--nolink'>Generate SSH key and copy to clipboard</span></button> and add the key to your [Bitbucket](https://bitbucket.org) account settings.

<img src='/img/documentation/integrations/bitbucket/generate-ssh.png' srcset='/img/documentation/integrations/bitbucket/generate-ssh@2x.png' class='center img-responsive img-bordered'>

***
## OAuth integration with Bitbucket
GitKraken's integration with Bitbucket provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/img/documentation/integrations/bitbucket/clone.png" srcset="/img/documentation/integrations/bitbucket/clone@2x.png" class="img-bordered img-responsive center">

Next, GitKraken Client presents a list of forks of the current repository when adding remotes:

<img src="/img/documentation/integrations/bitbucket/remote.png" srcset="/img/documentation/integrations/bitbucket/remote@2x.png" class="img-bordered img-responsive center">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple Bitbucket accounts

GitKraken connects to one Bitbucket account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated Bitbucket accounts.

***

## Training resources

Share these resources with your team to explain why collaborating with GitKraken Client is easier, and to get everyone up and running with Bitbucket and GitKraken Client quickly.


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