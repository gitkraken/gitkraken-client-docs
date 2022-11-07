---

title: GitKraken Client GitLab Issues Integration
description: Learn how to access GitLab Issues from GitKraken Git GUI
taxonomy:
    category: gitkraken-client

---

GitKraken Git GUI makes it easy to integrate with GitLab Issues.

<div class='callout callout--basic'>
    <p>The GitLab Issues integration is view-only for free users. To unlock all features for the GitLab Issues integration, consider upgrading to a <a href="https://gitkraken.com/pricing">paid GitKraken subscription</a>.</p>
</div>

***

### Connect GitLab Integration

The GitLab integration and GitLab Issues integration share the same connection. You can Set up the integration from the ISSUES pane in the left panel or from <kbd><i>Preferences   <i class='fa fa-caret-right'></i>   Integrations</i></kbd>.

<img src="/wp-content/uploads/connect-gitlab-issues.png" srcset="/wp-content/uploads/connect-gitlab-issues@2x.png" class="img-bordered img-responsive center">

<img src='/wp-content/uploads/preferences.png' class='center img-bordered'>

From the Integrations window, select _GitLab.com_ and then hit the <button class='button button--success button--ui button--nolink'>Connect to GitLab</button> button.

<img src="/wp-content/uploads/gitlab-authentication.png" srcset="/wp-content/uploads/gitlab-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open your default web browser where you can click <button class='button button--success button--ui button--nolink'>Continue authorization</button> and then log in with your GitLab credentials.

<img src="/wp-content/uploads/authorize-gitlab.png" srcset="/wp-content/uploads/authorize-gitlab@2x.png 2x" class="img-responsive center img-bordered">

<img src="/wp-content/uploads/gitlab-sign-in.png" srcset="/wp-content/uploads/gitlab-sign-in@2x.png 2x" class="img-responsive center img-bordered">

You'll then see a success message below and the connection will be active in GitKraken 🎉

<img src="/wp-content/uploads/auth-success-gitlab-1.png" srcset="/wp-content/uploads/auth-success-gitlab-1@2x.png 2x" class="img-responsive center img-bordered">

***

### Preview GitLab Issues

Once connected, your GitLab issues will start to appear in the left panel. You will initally see  _My Issues_ and _All Issues_ filters by default. You can edit or remove these as needed.

<img src="/wp-content/uploads/issue-list-gitlab.png" srcset="/wp-content/uploads/issue-list-gitlab@2x.png" class="img-bordered img-responsive center">

Hover over any issue to get a preview of the issue Title, Description, labels, milestones and assignee.

<img src="/wp-content/uploads/view-issue-gitlab.png" srcset="/wp-content/uploads/view-issue-gitlab@2x.png" class="img-bordered img-responsive center">

***

### View and Edit GitLab Issue Details

Click to select an issue to view the issue details.

<img src="/wp-content/uploads/gitlab-details.gif" class="img-bordered img-responsive center">

Here any edits made here will be reflected in your GitLab issues.

***

### Create New GitLab Issue

From the left panel, click the <button class='button button--success button--ui button--nolink'>+</button> icon to add a new GitLab issue.

<img src="/wp-content/uploads/new-gitlab-issue.png" srcset="/wp-content/uploads/new-gitlab-issue@2x.png" class="img-bordered img-responsive center">

Note that required fields are denoted by `*`. Your new issue will automatically sync with your GitLab issues.

***

### Create Filters

You may create filters to view the issues you need. We use the same syntax that GitLab uses for thier issues.

<img src="/wp-content/uploads/new-gitlab-filter.png" srcset="/wp-content/uploads/new-gitlab-filter@2x.png" class="img-bordered img-responsive center">

You can refer to [GitLab issue filtering](https://docs.gitlab.com/ee/user/search/index.html#filtering-issue-and-merge-request-lists) docs from GitLab for more information.

***

### Create Branches from Issue

You may create a branches tied to an issue from the issue details view <button class='button button--success button--ui button--nolink'>Create a branch for this issue</button> button. You can also right-click the issue or click the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd>.

<img src="/wp-content/uploads/create-branch-gitlab-issue.png" srcset="/wp-content/uploads/create-branch-gitlab-issue@2x.png" class="img-bordered img-responsive center">

The branch name will automatically prefill based on the issue name. After the branch is created, these branches will be denoted with the GitLab icon to reflect its link to a GitLab issue.

From here, it should be possible to configure triggers on the GitLab side for changes made to this branch.

***

### Copy Issue link or View in GitLab

You can quickly navigate to the issue in GitLab from the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> menu or by clicking <i class="fa fa-external-link" aria-hidden="true"></i> in the top right.

<img src="/wp-content/uploads/link-to-gitlab-issue.png" srcset="/wp-content/uploads/link-to-gitlab-issue@2x.png" class="img-bordered img-responsive center">


