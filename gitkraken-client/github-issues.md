---

title: GitHub Issues and GitKraken Git GUI
description: Learn how to access GitHub Issues from GitKraken Git GUI
taxonomy:
    category: gitkraken-client

---

GitKraken Git GUI makes it easy to integrate with GitHub Issues.

<div class='callout callout--basic'>
    <p>The GitHub Issues integration is view-only for free users. To unlock all features for the GitHub Issues integration, consider upgrading to <a href="https://gitkraken.com/pricing"> GitKraken Pro </a>. </p>
</div>

### Connect GitHub Integration

The GitHub integration and GitHub Issues integration share the same connection. You can Set up the integration from the ISSUES pane in the left panel or from <kbd><i>Preferences   <i class='fa fa-caret-right'></i>   Integrations</i></kbd>.

<img src="/img/documentation/integrations/github-issues/connect-github-issues.png" srcset="/img/documentation/integrations/github-issues/connect-github-issues@2x.png" class="img-bordered img-responsive center">

<img src='/img/documentation/integrations/github/preferences.png' class='center img-bordered'>

From the Integrations window, select _GitHub.com_ and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitHub</button> button.

<img src="/img/documentation/integrations/github/preferences-authentication.png" srcset="/img/documentation/integrations/github/preferences-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open your default web browser where you can click <button class='button button--success button--ui button--nolink'>Continue authorization</button> and then log in with your GitHub credentials.

You'll then see a success message below and the connection will be active in GitKraken 🎉

<img src="/img/documentation/integrations/github/github-success.png" srcset="/img/documentation/integrations/github/github-success@2x.png 2x" class="img-responsive center img-bordered">


### Preview GitHub Issues

Once connected, your GitHub issues will start to appear in the left panel. You will initally see  _My Open Issues_ and _All Open Issues_ filters by default. You can edit or remove these as needed.

<img src="/img/documentation/integrations/github-issues/issues-panel.png" srcset="/img/documentation/integrations/github-issues/issues-panel@2x.png" class="img-bordered img-responsive center">

Hover over any issue to get a preview of the issue Title, Description, Status, Labels, Assignees and Reporter.

<img src="/img/documentation/integrations/github-issues/issues-preview.png" srcset="/img/documentation/integrations/github-issues/issues-preview@2x.png" class="img-bordered img-responsive center">

### View and Edit GitHub Issue Details

Click to select an issue to view the issue details. 

<img src="/img/documentation/integrations/github-issues/github-details.gif" class="img-bordered img-responsive center">

Here any edits made here will be reflected in your GitHub issues.

### Create New GitHub Issue

From the left panel, click the <button class='button button--success button--ui button--nolink'>+</button> icon to add a new GitHub issue.

<img src="/img/documentation/integrations/github-issues/new-issue.png" srcset="/img/documentation/integrations/github-issues/new-issue@2x.png" class="img-bordered img-responsive center">

Note that required fields are denoted by `*`. Your new issue will automatically be added to your GitHub issues.

### Create Filters

You may create filters to view the issues you need. We use the same syntax that GitHub uses for thier issues.

<img src="/img/documentation/integrations/github-issues/new-filter.png" srcset="/img/documentation/integrations/github-issues/new-filter@2x.png" class="img-bordered img-responsive center">

You can refer to [GitHub issue filtering](https://docs.github.com/en/github/searching-for-information-on-github/searching-issues-and-pull-requests) docs from GitHub for more information.

### Create Branches from Issue

You may create a branches tied to an issue from the issue details view <button class='button button--success button--ui button--nolink'>Create a branch for this issue</button> button. You can also right-click the issue or click the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd>. 

<img src="/img/documentation/integrations/github-issues/create-branch.png" srcset="/img/documentation/integrations/github-issues/create-branch@2x.png" class="img-bordered img-responsive center">

The branch name will automatically prefill based on the issue name. After the branch is created, these branches will be denoted with the GitHub icon to reflect its link to a GitHub issue.

From here, it should be possible to configure triggers on the GitHub side for changes made to this branch.

### Copy Issue link or View in GitHub

You can quickly navigate to the issue in GitHub from the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> menu or by clicking <i class="fa fa-external-link" aria-hidden="true"></i> in the top right.

<img src="/img/documentation/integrations/github-issues/view-issue.png" srcset="/img/documentation/integrations/github-issues/view-issue@2x.png" class="img-bordered img-responsive center">


