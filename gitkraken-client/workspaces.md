---

title: Workspaces
description: Workspaces allow you to create groups of repositories.
taxonomy:
    category: gitkraken-client

---

GitKraken Workspaces allow you to create easily accessible groups of repositories, take action across multiple repos, view details about their state at a glance, and share them with your team.

<div class='callout callout--warning'>
    <p>
        <strong>Note:</strong>
            To create a Workspace, the integration for the desired service must be connected under <kbd>Preferences > Integrations</kbd>.
    </p>
</div>

***

## Create a workspace

To create a Workspace, navigate to the Workspaces tab. If this is your first time creating one, select <button class="button button--success button--ui button--nolink">+ Create Worspace</button>. Otherwise, select <button class="button button--success button--ui button--nolink">+ New Workspace</button>.

You can give the Workspace a name, icon, description, and make it personal or shared with your organization. Under _Add repositories_, select which hosting service these repositories will be from. If you have not connected the integration, selecting that service will take you to the integration connection. Finally, select the desired repositories for the workspace and then <button class="button button--success button--ui button--nolink">Create Workspace</button>.

<img src="/wp-content/uploads/create-workspace.gif" class="img-bordered img-responsive center">

## Workspace type

Workspaces are available as either a _Personal_ or _Team_ type.

**Personal Workspaces** are only accessible by you on this machine.

**Team Workspaces** will be available for the selected teams within your organization. This helps ensure that everyone is up-to-date on the same set of repositories by offering [multi-repository actions](/gitkraken-client/workspaces/#multi-repository-actions) and the ability to [work with all pull requests](/working-with-repositories/workspaces/#pull-requests) from these repositories. 

<img src="/wp-content/uploads/workspace-type.png" srcset="/wp-content/uploads/workspace-type@2x.png" class="img-bordered img-responsive center">

Learn more about [how to create a team](/start-here/teams/). 

## Edit a workspace

Edit a workspace by selecting the ellipsis <i class="fas fa-ellipsis-v"></i> icon by the Workspace name.

<img src="/wp-content/uploads/edit-a-workspace.png" srcset="/wp-content/uploads/edit-a-workspace@2x.png" class="img-bordered img-responsive center">

## Multi-repository actions

All repositories in a Workspace can be cloned, fetched, or opened at once, making it easy to get a new member of your team onboarded quickly or keep repository information up-to-date. Repositories can be effortlessly opened in GitKraken, in your <a href="/start-here/preferences/#external-editor">default editor</a>, or on their hosting service.

To perform an action on multiple repositories, select the check box next to the repository name and then select the desired action from the options at the top.

<img src="/wp-content/uploads/multi-action.png" srcset="/wp-content/uploads/multi-action@2x.png" class="img-bordered img-responsive center">

## Repository statuses

Workspaces expose the state of all repositories so you can see the last checked-out branch, how many commits are ahead or behind the remote, and your work in progress with counts of modified added, deleted, and renamed files.

<img src="/wp-content/uploads/repos-status.png" srcset="/wp-content/uploads/repos-status@2x.png" class="img-bordered img-responsive center">

## Workspace breadcrumb in toolbar

The option to remove the Workspace breadcrumb in the toolbar can be toggled under <kbd> Preferences > UI Customization > _Show Workspace breadcrumb in toolbar_</kbd>.

<img src="/wp-content/uploads/breadcrumb-setting.png" srcset="/wp-content/uploads/breadcrumb-setting@2x.png" class="img-bordered img-responsive center">

## View Repository Details

You may select the <i class="fa-solid fa-list"></i> icon to open the repository details.

<img src="/_images/repository-details.png" srcset="/_images/repository-details@2x.png" class="img-bordered img-responsive center">

## Pull requests

The Pull Request section will show all open pull requests for all repositories within the selected workspace. Information shown here includes the pull request title, pull request number, CI status, the name of the branch being merged, and number of comments.

To view a workspaces pull requests, select a workspace and then select `Pull Requests`.

<img src="/wp-content/uploads/pull-requests.png" srcset="/wp-content/uploads/pull-requests@2x.png" class="img-bordered img-responsive center">

Select `Filter pull requests` to filter for pull requests with the following options:

* "Opened by Me", to show pull requests that were opened by the user. This filter is available for GitHub, GitHub Enterprise, GitLab, and GitLab Self-Managed repositories.
* "At Risk", to show any pull requests that are not drafts and have been open for longer than 7 days. This filter is currently only available for GitHub, GitHub Enterprise, GitLab, and GitLab Self-Managed repositories.
* "By repository", to limit the view to a single repo within the Workspace. This filter is currently available for Azure DevOps, GitHub, GitHub Enterprise, Gitlab, and Gitlab Self-Managed repositories.

The search allows searching by pull request titles for all services. For GitHub.com workspaces, <a href="https://docs.github.com/en/search-github/searching-on-github/searching-issues-and-pull-requests">GitHub's search syntax</a> can also be used.

<img src="/wp-content/uploads/filter-and-search.png" srcset="/wp-content/uploads/filter-and-search@2x.png" class="img-bordered img-responsive center">


At risk pull requests are pull requests that have not been updated in more than 7 days. This is indicated by the `At risk` label.

<img src="/wp-content/uploads/at-risk.png" srcset="/wp-content/uploads/at-risk@2x.png" class="img-bordered img-responsive center">

### GitHub pull request view

If you are working with a GitHub.com workspace, you may select a pull request to work with the <a href="/working-with-repositories/pull-requests/#github-pull-request-view">GitHub pull request view</a>.

<img src="/wp-content/uploads/github-pull-request.png" srcset="/wp-content/uploads/github-pull-request@2x.png" class="img-bordered img-responsive center">