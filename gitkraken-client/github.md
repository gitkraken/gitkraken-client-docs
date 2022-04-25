---

title: GitHub
fescription: Integrate GitKraken with you GitHub repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken allows you to create an account and authenticate with GitHub, which will help you find repos on GitHub when cloning or adding your remotes.

**Benefits**

* Login to GitKraken using your GitHub account
* Create repositories on GitHub account including .gitignore and license
* Automatically generate an SSH key pair and add it to GitHub
* [Fork repositories](/working-with-repositories/fork/) from GitKraken
* Save authentication into profiles
* Clone from GitHub repo list
* Add remotes for GitHub repos
* Create and work with [Pull Requests](/working-with-repositories/pull-requests/#assignee-labels-and-reviewers)

<div class='embed-container embed-container--16-9'>
    <iframe width='560' height='315' src='https://www.youtube.com/embed/5nhNfMcczlQ?rel=0&vq=hd1080' frameborder='0' allowfullscreen></iframe>
</div>

***
## Sign in with GitHub

GitKraken lets you log in with your GitHub account.  Yay, one less password to remember 🎉

When logging into GitKraken, click <button class='button button--uiblue button--ui button--nolink'>Sign in with GitHub</button>  and log in with your credentials.  This will automatically connect your account for the GitHub integration.

<img src='/img/documentation/integrations/github/menu-login.png' class='center img-responsive img-bordered'>

***
## GitHub Authentication

To authenticate with GitHub, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/img/documentation/integrations/github/preferences.png" srcset="/img/documentation/integrations/github/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/img/documentation/integrations/customize.png" srcset="/img/documentation/integrations/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select **GitHub.com** and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitHub</button> button.

<img src="/img/documentation/integrations/github/preferences-authentication.png" srcset="/img/documentation/integrations/github/preferences-authentication@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you first log in with your GitHub credentials to allow GitKraken access.

Upon login, a success message appears and the connection will be active in GitKraken.

<img src="/img/documentation/integrations/github/github-success.png" srcset="/img/documentation/integrations/github/github-success@2x.png" class="img-bordered img-responsive center">

### Generating an SSH Key for GitHub
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitHub-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitHub account has been connected to GitKraken, generate an SSH key and add it to your GitHub account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

Click the magic <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitHub</button> button and watch what used to be 8 steps be completed in one.

Alternatively, add a key from  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitHub</button> or an existing key pair through _Add existing SSH key_.

<img src="/img/documentation/integrations/github/generate-ssh.png" srcset="/img/documentation/integrations/github/generate-ssh@2x.png" class="img-bordered img-responsive center">

***
## OAuth integration with GitHub
GitKraken's integration with Github provides handy information and features when working on your repositories.

See your existing repositories listed for easier cloning:

<img src="/img/documentation/integrations/github/clone.png" srcset="/img/documentation/integrations/github/clone@2x.png" class="img-bordered img-responsive center">

A list of forks of the current repository when adding remotes:

<img src="/img/documentation/integrations/github/remote.png" srcset="/img/documentation/integrations/github/remote@2x.png" class="img-bordered img-responsive center">

### Pull requests

Create [Pull Requests](/working-with-repositories/pull-requests/#assignee-labels-and-reviewers) directly in GitKraken - including adding reviewers, assisgnees, and labels.

<img src="/img/documentation/integrations/github/pull-request-create.png" srcset="/img/documentation/integrations/github/pull-request-create@2x.png" class="img-bordered img-responsive center">


### Pull request view

Click on a pull request in the left panel to access the pull request view.

<img src='/img/documentation/repositories/github-pr-view.png' srcset='/img/documentation/repositories/github-pr-view@2x.png' class='img-bordered img-responsive center'>

From this view, GitHub users may edit the pull request:

- Title
- Description
- Reviewers 
- Assignees
- Milestones
- Labels

From the upper right of the Pull Request view, you may click the <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>View file changes</span></button> button to review the affected files for this pull request. Note, code review and code comment are not currently available from within GitKraken Client.

<img src='/img/documentation/repositories/view-changes.png' srcset='/img/documentation/repositories/view-changes@2x.png' class='img-bordered img-responsive center'>

#### Comment on GitHub pull requests
Users may comment on a pull request -- which is great for submitting reviews, approving pull requests, or requesting changes. You may also use the refresh icon in the top right to quickly refresh the comments feed.

<img src='/img/documentation/repositories/refresh-comments.png' srcset='/img/documentation/repositories/refresh-comments@2x.png' class='img-bordered img-responsive center'>

You can also quote other comments in your reply from the elipsies <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> menu

<img src='/img/documentation/repositories/quote-reply.png' srcset='/img/documentation/repositories/quote-reply@2x.png' class='img-bordered img-responsive center'>

#### Branch checkout, build status, and adding remote
If you double-click the branch name in the bottom right of the PR view, GitKraken Client will automatically check out the branch and open the graph. 

If you click on the build status, GitKraken Client will take you to the build URL in your default web browser.

<img src='/img/documentation/repositories/build-status.png' srcset='/img/documentation/repositories/build-status@2x.png' class='img-bordered img-responsive center'>

Additionally if you have not added the remote, GitKraken Client will ask if you wish to add the remote to the app (which should help you review changes locally). 

#### Merging within pull request view

GitHub users may also merge a pull request by clicking the <button class='button button--success button--ui button--nolink'>Merge pull request</button> button from within GitKraken Client. 

<img src='/img/documentation/repositories/merge-options.png' srcset='/img/documentation/repositories/merge-options@2x.png' class='img-bordered img-responsive center'>

By default, the merge will default to the <kbd>Create a merge commit</kbd> setting, however you may also choose between <kbd>Squash and merge</kbd> and the <kbd>Rebase and merge</kbd>,

<div class='callout callout--basic'>
  <p>Not seeing something update in the pull request view? Try refreshing GitKraken Client to get the latest updates.</p>
</div>

### Why can't I see my remotes or repositories in the drop down menu?

If no remotes or repositories are appearing in Add Remote or Clone, you may need an organization to first allow access.  

<img src="/img/documentation/integrations/github/error.png" class="img-bordered img-responsive center">

GitKraken cannot see those repos when cloning or adding a fork unless the org specifically gives permission to GitKraken as an application.

* First check to see if access is allowed to GitKraken from your profile's [GitHub Applications](https://github.com/settings/connections/applications/a7557949433b7d282a76)
* If access has been allowed, then the organization will need to allow [Organization Approval](https://help.github.com/articles/requesting-organization-approval-for-your-authorized-applications/)
* If you are attempting to use GitKraken with a repository owned by a different individual, consider forking their repository to use GitKraken for your changes. Otherwise this other individual will need to first [install GitKraken](https://gitkraken.com) and connect it to GitHub (as shown in this page above) to authorize GitKraken.
* For details about third-party application restrictions view [Third-party apps list](https://help.github.com/articles/about-third-party-application-restrictions/)

### GitHub Actions

Check out [GitHub Actions](/git-workflows-and-extensions/github-actions/) for more information.

***

## Connecting to multiple GitHub accounts

GitKraken connects to one GitHub account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitHub accounts.

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