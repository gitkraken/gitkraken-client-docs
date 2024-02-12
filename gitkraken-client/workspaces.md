---

title: Workspaces
description: Workspaces allow you to create groups of repositories.
taxonomy:
    category: gitkraken-client

---

GitKraken Workspaces allow you to create easily accessible groups of repositories, take action across multiple repos, view details about their state at a glance, and share them with your team.

***

## Access Workspaces

To access Workspaces, select the Workspace tab in the top left or use the Command Palette (`command/ctrl + shift + P`) and search "Open Workspaces".

<img src="/wp-content/uploads/access-workspaces.png" srcset="/wp-content/uploads/access-workspaces@2x.png" class="img-bordered img-responsive center">

***

## Cloud Workspaces

Cloud Workspaces will be available for you to work with on any machine and the selected [teams](/start-here/teams/) within your organization. This helps ensure that everyone is up-to-date on the same set of repositories by offering [multi-repository actions](/gitkraken-client/workspaces/#cloud-multi-repository-actions) and the ability to [work with all pull requests](/gitkraken-client/workspaces/#pull-requests) from these repositories. 

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/OIQVsNRqg1M?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

### Create a Cloud Workspace

To create a Cloud Workspace, select <button class="button button--success button--ui button--nolink">+ New Workspace</button> (or <button class="button button--success button--ui button--nolink">+ Create a Worspace</button>). Then, select "Cloud Workspace”, name your Workspace, selecting the hosting service, and then select repositories to add. Optionally, you can also provide an icon, description and select teams or individual users to share with.

<img src="/wp-content/uploads/create-cloud-workspace.gif" class="img-bordered img-responsive center">

<div class='callout callout--warning'>
    <p>
        <strong>Note:</strong>
            The integration for the desired service must be connected under <kbd>Preferences > Integrations</kbd> to create a Cloud Workspace.
    </p>
</div>

### Cloud multi-repository actions

Actions can be performed on multiple repositories within the Workspace at once, making it easy to get a new member of your team onboarded quickly or keep repository information up-to-date. To perform an action on multiple repositories, select the check box next to the repository name and then select the desired action from the options at the top.

<img src="/wp-content/uploads/gkc-cloud-workspace-multi-action.png" class="img-bordered img-responsive center">

The following multi-repository actions can be performed:
- Clone: clone all selected repositories. HTTPS will be used by default unless you have SSH configured in your [Integration settings](https://help.gitkraken.com/gitkraken-client/integrations/). 
- Fetch: fetch all selected repositories.
- Pull: pull all selected repositories. You can change the behavior of the pull button by selecting the dropdown and selecting the radio button next to the desired option.
- Open in GitKraken Client or an external editor: open all selected repositories in GitKraken or in your [default editor](/start-here/preferences/#external-editor).
- Locate in filesystem: point to all selected repositories locally or update the local location of the repositories if they have changed. 
- Remove: remove all selected repositories from the Workspace.

### Pull requests

The Pull Request section will show all open pull requests for all repositories within the selected Workspace. Information shown here includes the pull request title, pull request number, CI status, complexity, the name of the branch being merged, and number of comments.

Complexity is a scale of 1 to 4 that scores a pull request’s complexity based on:
  - Number of lines changed
  - Number of files change
  - Number of commits made

To view a Workspaces pull requests, select a Workspace and then select `Pull Requests`.

<img src="/wp-content/uploads/pull-requests-2.png" srcset="/wp-content/uploads/pull-requests-2@2x.png" class="img-bordered img-responsive center">

Select `Filter pull requests` to filter for pull requests with the following options:

* "Opened by Me", to show pull requests that were opened by the user. This filter is available for GitHub, GitHub Enterprise Server, GitLab, and GitLab Self-Managed repositories.
* "At Risk", to show any pull requests that are not drafts and have been open for longer than 7 days. This filter is currently only available for GitHub, GitHub Enterprise Server, GitLab, and GitLab Self-Managed repositories.
* "By repository", to limit the view to a single repository within the Workspace. This filter is currently available for Azure DevOps, GitHub, GitHub Enterprise Server, Gitlab, and Gitlab Self-Managed repositories.

The search allows searching by pull request titles for all services. For GitHub.com Workspaces, <a href="https://docs.github.com/en/search-github/searching-on-github/searching-issues-and-pull-requests">GitHub's search syntax</a> can also be used.

<img src="/wp-content/uploads/filter-and-search-2.png" srcset="/wp-content/uploads/filter-and-search-2@2x.png" class="img-bordered img-responsive center">

At risk pull requests are pull requests that have not been updated in more than 7 days. This is indicated by the <i class="fa-solid fa-triangle-exclamation"></i> icon.

<img src="/wp-content/uploads/at-risk-1.png" srcset="/wp-content/uploads/at-risk-1@2x.png" class="img-bordered img-responsive center">

### GitHub pull request view

If you are working with a GitHub.com Workspace, you may select a pull request to work with the <a href="/working-with-repositories/pull-requests/#github-pull-request-view">GitHub pull request view</a>.

<img src="/wp-content/uploads/github-pull-request.png" srcset="/wp-content/uploads/github-pull-request@2x.png" class="img-bordered img-responsive center">

### Focus view

The Focus View displays all of your Pull Requests, Issues, and WIPs relevant to you for a selected workspace. You have a search bar to filter the results and columns that represent different states of the PRs, Issues, and WIPs.

<img src="/wp-content/uploads/focus_view2.0.gif" class="img-bordered img-responsive center">

* ALL: Shows all pull requests, issues, and WIPs for the repositories in selected Workspace.
* PRS: Shows all open pull requests for the repositories in selected Workspace.
* ISSUES: Shows all issues for the repositories in selected Workspace.
* WIPS: Shows all uncommitted changes for the repositories in selected Workspace.

You can filter the Pull Requests and Issues by the following:
* Filter PRs by `Mine`, `Created by Me`, `Assigned to Me`, or `Needs my review`.
* Filter ISSUES by `Mine`, `Created by Me`, `Assigned to Me`, or `Mentioned`.

Pull Requests and Issues can be pinned (and unpinned) by selecting the <i class="fa-solid fa-thumbtack"></i> icon to move them to the top of the list. Additionally, you have the option to Snooze PRs either indefinitely or for a specific duration by clicking the <i class="fa-solid fa-snooze"></i> icon, which will relocate them to the 'Snoozed' section. To retrieve these PRs, simply visit the 'Snoozed' section and remove them from the snooze state."

<img src="/wp-content/uploads/gkc-focus-view-9-12.gif" class="img-bordered img-responsive center">

From the Focus View, you can take action quickly on items such as:
- Merge pull request
- Close pull request
- Update issue status
- Mark issue as closed
- Open pull request/issue in the browser

<img src="/wp-content/uploads/gkc-focus-view-actions-9-12.png" class="img-bordered img-responsive center">

Instead of hunting for these pieces of information separately, you can get a holistic view of what you’re working on.

### Team view

On a Cloud Workspace, you will see a Team View section. This view shows all pull requests and issues for the repositories in your Workspace - giving you a high level view of your team's coding efforts. 

<img src="/wp-content/uploads/team-view@2x.png" class="img-bordered img-responsive center">

You can switch the Issue Tracker provider from the My Issues section in the Overview tab. 

<img src="/wp-content/uploads/9-2-team-issues-switch.png" srcset="/wp-content/uploads/9-2-team-issues-switch.png" class="img-bordered img-responsive center">

#### Team Pull Requests 

This section of the Team View will show all Pull Requests related to your selected team.

<img src="/wp-content/uploads/team-view-prs.png" srcset="/wp-content/uploads/team-view-prs@2x.png" class="img-bordered img-responsive center">

The Team Pull Requests section has the following columns:

* Last Updated 
* PR title with link to open the pull request in the hosting provider
* PR Author
* Repository name with link to open the reposotiry in GitKraken Client
* Review status
* PR status
  * Shows status for “Draft” or “At Risk” pull requests
* Checks - Shows CI/CD results
* Lines added/removed
* PR branch
  * Double click to check out directly in GitKraken Client
* GitHub.com Workspaces Only:
  * Shortcut to open the Pull Request Panel
  * Filter by assignee or author

<img src="/wp-content/uploads/8-9-team-pull-requests-columns.png" srcset="/wp-content/uploads/8-9-team-pull-requests-columns.png" class="img-bordered img-responsive center">

#### Team Issues 

Team Issues will show all GitHub Issues, GitLab Issues, Jira Cloud Issues, Jira Server, or Trello cards associated with the repo. 

With Team Issues it is easy to switch between Jira or Trello and back to either GitHub Issues or GitLab Issues. If you select Jira or Trello, you can also filter by project so that you only see issues that matter to you.

<img src="/wp-content/uploads/9-2-team-issues-switch.png" srcset="/wp-content/uploads/9-2-team-issues-switch.png" class="img-bordered img-responsive center">

View, edit and tie a branch to the issue with the Issue View from Workspace. 

<img src="/wp-content/uploads/issue-view-workspaces.png" srcset="/wp-content/uploads/issue-view-workspaces.png" class="img-bordered img-responsive center">

***

## Local Workspaces

Local Workspaces allow you to create easily accessible groups of repositories, take actions across multiple repositories, view details about their state at a glance, and share them with your team.

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/8xlbH2tNZwc?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

### Create a Local Workspace

To create a Local Workspace, select <button class="button button--success button--ui button--nolink">+ New Workspace</button> (or <button class="button button--success button--ui button--nolink">+ Create a Worspace</button>). Then, select “Local Workspace”, name your Workspace, and browse to select repositories to add to your Local Workspace. You may select individual repositories, a directory of repositories, or a VS Code Workspace (.code-workspace). Optionally, you can also provide an icon and description. 

<img src="/wp-content/uploads/create-local-workspace-1.gif" class="img-bordered img-responsive center">

### Local multi-repository actions

Actions can be performed on multiple repositories within the Workspace at once. To perform an action on multiple repositories, select the check box next to the repository name and then select the desired action from the options at the top.

The following multi-repository actions can be performed:
- Fetch: fetch all selected repositories.
- Pull: pull all selected repositories. You can change the behavior of the pull button by selecting the dropdown and selecting the radio button next to the desired option.
- Open in GitKraken Client or an external editor: open all selected repositories in GitKraken or in your [default editor](/start-here/preferences/#external-editor).
- Remove: remove all selected repositories from the Workspace.

### Create a Cloud Workspace from a Local Workspace

You can create a Cloud Workspace from a Local Workspace which will enable more visibility into your pull requests, issues, and share your Workspace with teams.

To do this, select your local Workspace to open it and then select `Create cloud workspace`. From here, you will need to select the provider for your new Cloud Workspace, select the repositories you would like added, and you can even add more repositories to this Workspace from the selected provider.

<img src="/wp-content/uploads/Create-cloud-workspace-2.png" class="img-bordered img-responsive center">

<div class='callout callout--warning'>
    <p>
        <strong>Note:</strong>
            The integration for the desired service must be connected under <kbd>Preferences > Integrations</kbd> to create a Cloud Workspace.
    </p>
</div>

***

## Edit a Workspace

Edit a Workspace by selecting the ellipsis <i class="fas fa-ellipsis-v"></i> icon by the Workspace name.

<img src="/wp-content/uploads/edit-a-workspace.png" srcset="/wp-content/uploads/edit-a-workspace@2x.png" class="img-bordered img-responsive center">

You can adjust the content you want displayed for each view by selecting the settings <i class="fas fa-cog"></i>.

<img src="/wp-content/uploads/configure-focus-view.png" class="img-bordered img-responsive center">

***

## View Repository Details

You may select the <i class="fa-solid fa-list"></i> icon to open the repository details.

<img src="/wp-content/uploads/repository-details.png" srcset="/wp-content/uploads/repository-details@2x.png" class="img-bordered img-responsive center">

***

## Repository statuses

Workspaces expose the state of all repositories so you can see the last checked-out branch, how many commits are ahead or behind the remote, and your work in progress with counts of modified added, deleted, and renamed files.

<img src="/wp-content/uploads/repos-status.png" srcset="/wp-content/uploads/repos-status@2x.png" class="img-bordered img-responsive center">

***

## Workspace breadcrumb in toolbar

The option to remove the Workspace breadcrumb in the toolbar can be toggled under <kbd> Preferences > UI Customization > _Show Workspace breadcrumb in toolbar_</kbd>.

<img src="/wp-content/uploads/breadcrumb-setting.png" srcset="/wp-content/uploads/breadcrumb-setting@2x.png" class="img-bordered img-responsive center">

## Requirement for Azure Workspaces and Insights

In order to work with Workspaces and [Insights](/gitkraken-client/insights/) for Azure, `Third-party application access via OAuth` will need to be enabled in Azure from `Organization Settings > Policies`. You can find more information on this setting [here](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/change-application-access-policies?view=azure-devops).