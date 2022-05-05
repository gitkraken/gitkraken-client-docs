---
Title: Azure DevOps
Description: Integrate GitKraken with your Azure DevOps (formerly VSTS) repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken allows you to connect to Azure DevOps (formerly VSTS), which will help you find repos on Azure DevOps when cloning.

**Benefits**

* Create repositories on Azure DevOps account including .gitignore and license
* Automatically generate an SSH key pair and copy it to Azure DevOps
* Clone from Azure DevOps repo list
* Identify Azure DevOps repos with remote avatars on graph
* Add remotes for Azure DevOps repos
* Create and view Pull Requests


***

## Azure DevOps Authentication

To authenticate with Azure DevOps, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Authentication window, enter your _Host Domain_ then click the <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>Generate a token on Azure DevOps</span></button>

<img src="/img/documentation/integrations/vsts/authentication.png" srcset="/img/documentation/integrations/vsts/authentication@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you next log in with your Azure DevOps credentials and generate an access token.

<img src="/img/documentation/integrations/vsts/accesstoken.png" srcset="/img/documentation/integrations/vsts/accesstoken@2x.png" class="img-bordered img-responsive center">

Copy your token to the clipboard as this is the only time you will see this token.  Paste the token into GitKraken and click on <button class='button button--success button--ui button--nolink'>Connect</button>.

<img src="/img/documentation/integrations/vsts/authentication-connect.png" srcset="/img/documentation/integrations/vsts/authentication-connect@2x.png" class="img-bordered img-responsive center">

### Generating an SSH Key for Azure DevOps
GitKraken uses your local SSH Config from _SSH Defaults_ to fetch and push unless you set up a Azure DevOps-specific SSH key, or enable your local SSH Agent.

Once your Azure DevOps account has been connected to GitKraken, you may easily generate an SSH key and add it to your Azure DevOps account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

Click the magic <button class='button button--success button--ui button--nolink'>Generate SSH key and copy to clipboard</button> button and add the key to your Azure DevOps account.

<img src="/img/documentation/integrations/vsts/vsts-ssh.png" srcset="/img/documentation/integrations/vsts/vsts-ssh@2x.png 2x" class="img-responsive center img-bordered">

***
## OAuth integration with Azure DevOps
GitKraken's integration with Azure DevOps provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/img/documentation/integrations/vsts/clone.png" srcset="/img/documentation/integrations/vsts/clone@2x.png" class="img-bordered img-responsive center">

Next, GitKraken presents a list of forks of the current repository when adding remotes:

<img src="/img/documentation/integrations/vsts/remote.png" srcset="/img/documentation/integrations/vsts/remote@2x.png" class="img-bordered img-responsive center">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple Azure DevOps accounts

GitKraken connects to one Azure DevOps account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated Azure DevOps accounts.

***

## Training resources

Share these resources with your team to explain why collaborating with GitKraken is easier, and to get everyone up and running with Azure DevOps and GitKraken quickly.


<div class='center'>
    <div class="flex-grid">
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/azure-devops#how-to-azure-devops-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/video-thumbs/azure-gitkraken.png'gitkraken-for-azure-cheat-sheet-2@2x.jpg 2x" alt='How to use Azure DevOps with GitKraken video thumbnail' style="height: 150px; width: auto; max-width: none;">
                <p>How to use Azure DevOps with GitKraken Video</p>
            </a>
        </div>
        <div class="flex-item">
            <a href='https://www.gitkraken.com/integrations/azure-devops#why-azure-devops-gitkraken' target='_blank' rel='noopener'>
                <img src='/img/downloads/gitkraken-azure-whitepaper.jpg' srcset="/img/downloads/gitkraken-azure-whitepaper@2x.jpg 2x" alt='GitKraken for Azure DevOps Users cover' style="height: 150px; width: auto; max-width: none;">
                <p>Azure DevOps White Paper<br />(PDF)</p>
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

