---

title: GitHub Enterprise
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

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, enter your _Host Domain_ then click the Generate an access token on _your URL_ link.

<img src="/img/documentation/integrations/github-enterprise/authentication.png" srcset="/img/documentation/integrations/github-enterprise/authentication@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you next log in with your GitHub Enterprise credentials and generate an access token.

<img src='/img/documentation/integrations/github-enterprise/accesstoken.png' class='center img-bordered'>

Copy your token to the clipboard as this is the only time you will see this token.  Paste the token into GitKraken and click on <button class='button button--success button--ui button--nolink'>Connect</button>.

<img src="/img/documentation/integrations/github-enterprise/authentication-connect.png" srcset="/img/documentation/integrations/github-enterprise/authentication-connect@2x.png" class="img-bordered img-responsive center">

### Generating an SSH Key for GitHub Enterprise
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitHub-specific SSH key, or enable your local SSH Agent.</p>
</div>
Once your GitHub Enterprise account has been connected to GitKraken, you may easily generate an SSH key and add it to your GitHub Enterprise account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src='/img/documentation/integrations/github-enterprise/ssh.png' srcset='/img/documentation/integrations/github-enterprise/ssh@2x.png' class='center img-responsive img-bordered'>

Click the <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitHub Enterprise</button> button and watch the magic happen.

Alternatively add existing  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitHub Enterprise</button> or an existing key pair through _Add existing SSH key_.

***

## Connecting to multiple GitHub Enterprise accounts

GitKraken connects to one GitHub Enterprise account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitHub Enterprise accounts.

***

## Training resources

Share these resources with your team to explain why collaborating with GitKraken is easier, and to get everyone up and running with GitHub and GitKraken quickly.


<div class='center'>
    <div class="flex-grid">
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/github#how-to-github-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/video-thumbs/github-gitkraken.png'gitkraken-for-github-cheat-sheet-2@2x.jpg 2x" alt='How to use GitHub with GitKraken video thumbnail' style="height: 150px; width: auto; max-width: none;">
                <p>How to use GitHub with GitKraken Video</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/github#why-github-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-github-whitepaper.jpg' srcset="/img/downloads/gitkraken-github-whitepaper@2x.jpg 2x" alt='GitKraken for GitHub Users cover' style="height: 150px; width: auto; max-width: none;">
                <p>GitHub White Paper<br />(PDF)</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/pdfs/gitkraken-for-github-cheat-sheet' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-for-github-cheat-sheet-2.jpg' srcset="/img/downloads/gitkraken-for-github-cheat-sheet-2@2x.jpg 2x" alt='GitKraken for GitHub Users cover' style="height: 150px; width: auto; max-width: none;">
                <p>GitHub Cheat Sheet<br />(PDF)</p>
            </a>
        </div>
    </div>
    <div class="flex-grid">
        <div class="flex-item">
        	<a href='https://www.gitkraken.com/pdfs/gitkraken-git-gui-cheat-sheet' target='_blank' rel='noopener'>
        	    <img src='/img/downloads/gitkraken-cheat-sheet.png' srcset="/img/downloads/gitkraken-cheat-sheet@2x.png 2x" alt='GitKraken Cheat Sheet cover' style="height: 150px; width: auto; max-width: none;">
        	    <p>GitKraken Cheat Sheet<br />(PDF)</p>
        	</a>
        </div>
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
    </div>
</div>