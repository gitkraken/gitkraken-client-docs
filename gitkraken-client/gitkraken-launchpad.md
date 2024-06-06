---

title: Launchpad
description: Launchpad presents an overview of your Pull Requests, Issues and WIPs.
taxonomy:
    category: gitkraken-client

---

The Launchpad displays all of your Pull Requests, Issues, and Works In Progress (WIPs) relevant to you for a selected filters. You have a search bar to filter the results and columns that represent different states of the PRs, Issues, and WIPs, and dropdown selectors for workspace-based filtering.

### Getting started with the Launchpad

The Launchpad tab can be found in the top-left corner. By default, it displays a list of your Pull Requests, WIPs and Issues for the selected Workspace directly from your Hosting Service and Issue Tracker.

#### Connect Integrations

Integrate your repositories, issues, and pull requests with the Launchpad to consolidate your workflow.

You can easily connect your integrations at <kbd>Preferences > Integrations</kbd>

<img src="/wp-content/uploads/gkc-launchpad-hosting-service-10-0-0.png" class="img-bordered img-responsive center">

#### Set up Workspaces and Integrations

Create a [Workspace](/gitkraken-client/workspaces/) with the relevant integration. Once created, you will be able to filter and focus on WIPs for specific repositories, issues, and pull requests.


<img src="/wp-content/uploads/gkc-launchpad-10-0-0.gif" class="img-bordered img-responsive center">

* PULL REQUESTS: Shows all open pull requests for the repositories in selected Workspace.
* ISSUES: Shows all issues for the repositories in selected Workspace.
* WIPS: Shows all uncommitted changes for the repositories in selected Workspace.
* ALL: Shows all pull requests, issues, and WIPs for the repositories in selected Workspace.


Pull Requests and Issues can be pinned (and unpinned) by selecting the <i class="fa-solid fa-thumbtack"></i> icon to move them to the top of the list. Additionally, you have the option to Snooze PRs either indefinitely or for a specific duration by clicking the <i class="fa-solid fa-snooze"></i> icon, which will relocate them to the 'Snoozed' section. To retrieve these PRs, simply visit the 'Snoozed' section and remove them from the snooze state."

<img src="/wp-content/uploads/gkc-launchpad-pinsnooze-10-0-0.gif" class="img-bordered img-responsive center">

### Personal or Team view

<img src="/wp-content/uploads/gkc-launchpad-personal-team-10.0.0.png" class="img-bordered img-responsive center">

The Launchpad can be viewed in Personal or Team mode. Personal mode displays only the items where you are involved (created by you, assigned to you or created by you), while Team mode shows all pull requests and issues for the repositories in your Workspace - giving you a high level view of your team's coding efforts. You can toggle between these views by selecting the corresponding icon in the top right corner of the Launchpad.

Note that Personal mode allows to see all items where you are involved in the remote hosting service, without limiting to a selected Workspace (select None in the Workspace dropdown). But Team mode requires a Workspace to be selected.

### Pull Requests

From the Launchpad, you can take action quickly on items such as:
- Merge pull request
- Close pull request
- Update issue status
- Mark issue as closed
- Open pull request/issue in the browser

<img src="/wp-content/uploads/gkc-launchpad-actions-10-0-0.png" class="img-bordered img-responsive center">

Pull Requests section has the following columns:

* Last Updated 
* Status
  * Pull Request status. Shows status for "Open", “Draft” or “At Risk” pull requests
  * Pending Review or Changes Requested
  * Build status
* PR title with link to open the pull request in the hosting provider
  * Lines added/removed
  * Code Suggestions
* People 
* Repository and branch
* Actions
  * Open Repository
  * Open Repository in browser
  * Open Code Suggestions
  * Review Pull Request (GitHub only)
  * Close Pull Request

#### Github Pull Requests

If you are working with a GitHub.com Workspace, you may select a pull request to work with the <a href="/working-with-repositories/pull-requests/#github-pull-request-view">GitHub pull request view</a>.


### Issues

You can switch the Issue Tracker provider from the Issues section. The Issue Tracker provider can be set up in the <kbd>Preferences > Integrations</kbd> tab.

<img src="/wp-content/uploads/gkc-launchpad-issues-10-0-0.png" class="img-bordered img-responsive center">

### WIPs

The WIPs section displays all uncommitted changes for the repositories in the selected Workspace. You can quickly open the repository in a repository tab by clicking on <button class="button button--success button--ui button--nolink">View Repo</button>.

### ALL

The ALL section displays all pull requests, issues, and WIPs for the repositories in the selected Workspace.

### SNOOZED

The SNOOZED section displays all snoozed pull requests and issues. You can unsnooze them by clicking on the <i class="fa-solid fa-snooze"></i> icon.