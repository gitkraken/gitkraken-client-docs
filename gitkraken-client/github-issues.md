---

title: GitKraken Client GitHub Issues Integration
description: Learn how to access GitHub Issues from GitKraken Git GUI
taxonomy:
    category: gitkraken-client

---

GitKraken Git GUI makes it easy to integrate with GitHub Issues.

<div class='callout callout--basic'>
    <p>The GitHub Issues integration is view-only for free users. To unlock all features for the GitHub Issues integration, consider upgrading to a <a href="https://gitkraken.com/pricing"> paid GitKraken license </a>. </p>
</div>

### Connect GitHub Integration

The GitHub integration and GitHub Issues integration share the same connection. You can Set up the integration from the ISSUES pane in the left panel or from <kbd><i>Preferences   <i class='fa fa-caret-right'></i>   Integrations</i></kbd>.

<img src="/wp-content/uploads/connect-github-issues.png" srcset="/wp-content/uploads/connect-github-issues@2x.png" class="img-bordered img-responsive center">

<img src='/wp-content/uploads/preferences.png' class='center img-bordered'>

From the Integrations window, select _GitHub.com_ and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitHub</button> button.

<img src="/wp-content/uploads/preferences-authentication.png" srcset="/wp-content/uploads/preferences-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open your default web browser where you can click <button class='button button--success button--ui button--nolink'>Continue authorization</button> and then log in with your GitHub credentials.

You'll then see a success message below and the connection will be active in GitKraken 🎉

<img src="/wp-content/uploads/github-success-1.png" srcset="/wp-content/uploads/github-success-1@2x.png 2x" class="img-responsive center img-bordered">


### Preview GitHub Issues

Once connected, your GitHub issues will start to appear in the left panel. You will initally see  _My Open Issues_ and _All Open Issues_ filters by default. You can edit or remove these as needed.

<img src="/wp-content/uploads/issues-panel-github-issues.png" srcset="/wp-content/uploads/issues-panel-github-issues@2x.png" class="img-bordered img-responsive center">

Hover over any issue to get a preview of the issue Title, Description, Status, Labels, Assignees and Reporter.

<img src="/wp-content/uploads/issues-preview-github-issues.png" srcset="/wp-content/uploads/issues-preview-github-issues@2x.png" class="img-bordered img-responsive center">

### View and Edit GitHub Issue Details

Click to select an issue to view the issue details.

<img src="/wp-content/uploads/github-details-github-issues.gif" class="img-bordered img-responsive center">

Here any edits made here will be reflected in your GitHub issues.

### Create New GitHub Issue

From the left panel, click the <button class='button button--success button--ui button--nolink'>+</button> icon to add a new GitHub issue.

<img src="/wp-content/uploads/new-issue-github-issues.png" srcset="/wp-content/uploads/new-issue-github-issues@2x.png" class="img-bordered img-responsive center">

Note that required fields are denoted by `*`. Your new issue will automatically be added to your GitHub issues.

### Create Filters

You may create filters to view the issues you need. We use the same syntax that GitHub uses for their issues.

<img src="/wp-content/uploads/new-filter-github-issues.png" srcset="/wp-content/uploads/new-filter-github-issues@2x.png" class="img-bordered img-responsive center">

You can refer to [GitHub issue filtering](https://docs.github.com/en/github/searching-for-information-on-github/searching-issues-and-pull-requests) docs from GitHub for more information.

### Create Branches from Issue

You may create a branches tied to an issue from the issue details view <button class='button button--success button--ui button--nolink'>Create a branch for this issue</button> button. You can also right-click the issue or click the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd>.

<img src="/wp-content/uploads/create-branch-github-issues.png" srcset="/wp-content/uploads/create-branch-github-issues@2x.png" class="img-bordered img-responsive center">

The branch name will automatically prefill based on the issue name. After the branch is created, these branches will be denoted with the GitHub icon to reflect its link to a GitHub issue.

From here, it should be possible to configure triggers on the GitHub side for changes made to this branch.

### Copy Issue link or View in GitHub

You can quickly navigate to the issue in GitHub from the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> menu or by clicking <i class="fa fa-external-link" aria-hidden="true"></i> in the top right.

<img src="/wp-content/uploads/view-issue-github-issues.png" srcset="/wp-content/uploads/view-issue-github-issues@2x.png" class="img-bordered img-responsive center">


