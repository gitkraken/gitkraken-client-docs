---

title: Jira and GitKraken Git GUI
description: Learn how to access Jira Issues from GitKraken Git GUI
taxonomy:
    category: gitkraken-client

---

GitKraken Git GUI makes it easy to integrate with Jira Cloud and Jira Server.

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/On83cso-w3U" frameborder="0" allowfullscreen></iframe>
</div>

<div class='callout callout--basic'>
    <p>The Jira integration is view-only for free users. To unlock all features for the Jira integration, consider upgrading to <a href="https://gitkraken.com/pricing"> GitKraken Pro </a>. </p>
</div>
***

### Connect Jira Integration

Set up the integration from the ISSUES pane in the left panel or from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src="/img/documentation/integrations/jira/connect-jira.png" srcset="/img/documentation/integrations/jira/connect-jira@2x.png" class="img-bordered img-responsive center">

You will then be prompted by an Atlassian page to allow GitKraken Git GUI to connect to your Jira account. Hit <em>Accept</em> to proceed.

<img src="/img/documentation/integrations/jira/atlassian.png" srcset="/img/documentation/integrations/jira/atlassian@2x.png" class="img-bordered img-responsive center">

Alternatively, you may copy the token from the _Success_ page and paste it into the Jira Cloud integration page inside GitKraken Git GUI. 

***

### Preview Jira Issues

Once connected, your Jira issues will start to appear in the left panel. The app will default to a _My Issues_ filter which will show issues assigned to you.

<img src="/img/documentation/integrations/jira/issue-list.png" srcset="/img/documentation/integrations/jira/issue-list@2x.png" class="img-bordered img-responsive center">

Hover over any issue to get a preview of the issue Title, Description, Status, Assignee, and Reporter.

<img src="/img/documentation/integrations/jira/view-issue.png" srcset="/img/documentation/integrations/jira/view-issue@2x.png" class="img-bordered img-responsive center">

***

### View Jira Issue Details

Click to select an issue to view the issue details. 

<img src="/img/documentation/integrations/jira/issue-details.gif" class="img-bordered img-responsive center">

Here you may view and edit:
 
 - Title and Description
 - Status
 - Assignee
 - Add comments

Any changes made here will be reflected in your Jira board.

***

### Create New Jira Issue

From the left panel, click the <button class='button button--success button--ui button--nolink'>+</button> icon to add a new Jira issue.

<img src="/img/documentation/integrations/jira/create-issue.gif" class="img-bordered img-responsive center">

Your new issue will automatically sync with your Jira project.

***

### Create Filters

You may create filters to view the issues you need. Atlassian uses JQL syntax for filters, and the integration will help you auto-complete your filter fields.

<img src="/img/documentation/integrations/jira/create-filter.png" srcset="/img/documentation/integrations/jira/create-filter@2x.png" class="img-bordered img-responsive center">

However for more details about how to write your JQL filters, please refer to the [Get started with Advanced Search and JQL](https://www.atlassian.com/software/jira/guides/expand-jira/jql#visualize-results) guide by Atlassian.

***

### Create Branches from Issue

You may create a branches tied to an issue from the issue details view. 

<img src="/img/documentation/integrations/jira/create-branch.gif" class="img-bordered img-responsive center">

The branch name will automatically prefill based on the issue name. After the branch is created, these branches will be denoted with the Jira icon to reflect its link to a Jira issue.

From here, it should be possible to configure triggers on the Jira side for changes made to this branch.

***

### Copy Issue link or View in Jira

Click the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> icon to copy the issue link or view the item directly in Jira.

<img src="/img/documentation/integrations/jira/view-issue-in-jira.png" srcset="/img/documentation/integrations/jira/view-issue-in-jira@2x.png" class="img-bordered img-responsive center">

### Git Integration for Jira

For even more goodness between GitKraken and Jira, check out our additional integration features with <a href="/integrations/git-integration-for-jira">Git Integration for Jira</a>.
