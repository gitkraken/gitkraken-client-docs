---

title: GitKraken Desktop GitHub Integration
description: Integrate GitKraken with you GitHub repository by following these steps.
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

<img src='/wp-content/uploads/menu-login.png' class='center img-responsive img-bordered'>

***
## GitHub Authentication

To authenticate with GitHub, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select **GitHub.com** and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitHub</button> button.

<img src="/wp-content/uploads/preferences-authentication.png" srcset="/wp-content/uploads/preferences-authentication@2x.png" class="img-bordered img-responsive center">

This opens a web browser where you first log in with your GitHub credentials to allow GitKraken access.

Upon login, a success message appears. Finish connecting by selecting `Open GitKraken`. 

<img src="/wp-content/uploads/github-success-1.png" srcset="/wp-content/uploads/github-success-1@2x.png" class="img-bordered img-responsive center">

Alternativley, you can connect the integration by copy and pasting the OAuth token manually. 
 
<img src="/wp-content/uploads/github-oauth-token.png" class="img-bordered img-responsive center"> 

### Generating an SSH Key for GitHub
<div class='callout callout'>
    <p>Note 📝 - GitKraken uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a GitHub-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your GitHub account has been connected to GitKraken, generate an SSH key and add it to your GitHub account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

Click the magic <button class='button button--success button--ui button--nolink'>Generate SSH key and add to GitHub</button> button and watch what used to be 8 steps be completed in one.

Alternatively, add a key from  _SSH Defaults_ with <button class='button button--uiorange button--ui button--nolink'>Add key to GitHub</button> or an existing key pair through _Add existing SSH key_.

<img src="/wp-content/uploads/generate-ssh.png" srcset="/wp-content/uploads/generate-ssh@2x.png" class="img-bordered img-responsive center">

***
## OAuth integration with GitHub
GitKraken's integration with Github provides handy information and features when working on your repositories.

See your existing repositories listed for easier cloning:

<img src="/wp-content/uploads/clone.png" srcset="/wp-content/uploads/clone@2x.png" class="img-bordered img-responsive center">

A list of forks of the current repository when adding remotes:

<img src="/wp-content/uploads/remote.png" srcset="/wp-content/uploads/remote@2x.png" class="img-bordered img-responsive center">

### Pull requests

Create [Pull Requests](/working-with-repositories/pull-requests/#assignee-labels-and-reviewers) directly in GitKraken - including adding reviewers, assisgnees, and labels.

<img src="/wp-content/uploads/pull-request-create.png" srcset="/wp-content/uploads/pull-request-create@2x.png" class="img-bordered img-responsive center">


## GitHub pull request view

GitHub.com users may utilize the pull request view for GitHub pull requests.

To enable this feature, first set up the [GitHub integration](/gitkraken-client/github-gitkraken-client/). Then with a GitHub repo open inside of GitKraken Desktop, select a pull request in the left panel (or checkout the source branch and a PR icon with the number shows up next to the branch) to bring up the pull request view. Or from the Launchpad, click on the icon at the right side of the Pull Request.

Repository tab:
<img src='/wp-content/uploads/gkc-github-pr-view.png' class='img-bordered img-responsive center'>

Launchpad:

<img src='/wp-content/uploads/gkc-launchpad-pr-actions.png' class='img-bordered img-responsive center'>

From this view, GitHub users may edit the pull request:

- Title
- Description
- Reviewers
- Assignees
- Milestones
- Labels


From the upper right of the Pull Request view, you may click the <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>Review Code and Suggest Changes</span></button> button to review the affected files for this pull request. Note, code review and code comment are not currently available from within GitKraken Desktop.

<img src='/wp-content/uploads/gkc-pr-code-suggestions.png' class='img-bordered img-responsive center'>

### Review Code and Suggest Changes

In Gitkraken Desktop, Review Code and Suggest Changes simplifies code review by allowing you to make suggestions and edits across the entire project, not just on the lines that were changed, GitKraken Desktop, and gitkraken.dev. When a Pull Request is open, you can make suggestions to the pull request that others can then review and accept to include in the pull request. 

Open the Pull Request and click on <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>Edit to Suggest Changes to PR #XX</span></button>, edit the file, save changes and click on <button class='button button--success button--ui button--nolink'>Suggest X file change to PR #XX </button>

<img src='/wp-content/uploads/gkc-pr-suggest-code-changes.gif' class='img-bordered img-responsive center'>

### Accept or Reject Code Suggestions

In the Github Pull Request panel, you have the ability to review, accept or reject your teammate's code suggestions.
A Pull Request with Code Suggestions has the <em class='context-menu'>Code Suggestions</em> label in it:

<img src='/wp-content/uploads/gkc-pr-code-suggestions2.png' class='img-bordered img-responsive center'>

Clicking on one of the Code Suggestions opens the repo tab. The right panel shows a diff with the changes so you can review and two options on bottom `Apply suggestion to branch` or `Reject suggestion`.

<img src='/wp-content/uploads/gkc-pr-code-suggestions-apply.gif' class='img-bordered img-responsive center'>
#### Branch checkout, build status, and adding remote
If you double-click the branch name in the bottom right of the PR view, GitKraken Desktop will automatically check out the branch and open the graph.

If you click on the build status, GitKraken Desktop will take you to the build URL in your default web browser.

<img src='/wp-content/uploads//build-status.png' srcset='/wp-content/uploads//build-status@2x.png' class='img-bordered img-responsive center'>

Additionally if you have not added the remote, GitKraken Desktop will ask if you wish to add the remote to the app (which should help you review changes locally).

#### Merging within pull request view

GitHub users may also merge a pull request by clicking the <button class='button button--success button--ui button--nolink'>Merge pull request</button> button from within GitKraken Desktop.

<img src='/wp-content/uploads//merge-options.png' srcset='/wp-content/uploads//merge-options@2x.png' class='img-bordered img-responsive center'>

By default, the merge will default to the <kbd>Create a merge commit</kbd> setting, however you may also choose between <kbd>Squash and merge</kbd> and the <kbd>Rebase and merge</kbd>.

<div class='callout callout--basic'>
  <p>Not seeing something update in the pull request view? Try refreshing GitKraken Desktop to get the latest updates.</p>
</div>

### Why can't I see my remotes or repositories in the drop down menu?

If no remotes or repositories are appearing in Add Remote or Clone, you may need an organization to first allow access.

<img src="/wp-content/uploads/error.png" class="img-bordered img-responsive center">

GitKraken cannot see those repos when cloning or adding a fork unless the org specifically gives permission to GitKraken as an application.

* First check to see if access is allowed to GitKraken from your profile's [GitHub Applications](https://github.com/settings/connections/applications/a7557949433b7d282a76)
* If access has been allowed, then the organization will need to allow [Organization Approval](https://help.github.com/articles/requesting-organization-approval-for-your-authorized-applications/)
* If you are attempting to use GitKraken with a repository owned by a different individual, consider forking their repository to use GitKraken for your changes. Otherwise this other individual will need to first [install GitKraken](/gitkraken-client/how-to-install/) and connect it to GitHub (as shown in this page above) to authorize GitKraken.
* For details about third-party application restrictions view [Third-party apps list](https://help.github.com/articles/about-third-party-application-restrictions/)

### GitHub Actions

Check out [GitHub Actions](/git-workflows-and-extensions/github-actions/) for more information.

***

## Connecting to multiple GitHub accounts

GitKraken connects to one GitHub account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated GitHub accounts.
