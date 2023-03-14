---

title: GitKraken Client Release Notes
description: View a history of the new features and fixes in GitKraken Client's Version 8.
og_image: /img/GitKrakenClient-Hero.png
taxonomy:
    category: gitkraken-client

---

Behold the evolution of GitKraken Client! Find out what&rsquo;s new, what&rsquo;s fixed, or just take a trip down memory lane with a nostalgic swagger, remembering those bugs of yesterday.

<a href="https://www.gitkraken.com/download" target="_blank" class="button button--basic ">Download Current Version Now</a>

Check out our [GitKraken Roadmap](https://www.gitkraken.com/git-client/roadmap) to see what we’re working on.


***

<a id="v9-2-0"></a>
## Version 9.2.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ZL2Mj8yDI-I" frameborder="0" allowfullscreen></iframe>
</div>

_“Hocus Focus!”_

_Read the [full release notes](https://help.gitkraken.com/gitkraken-client/current/#version-9-2) and see how it all works!_

### Tuesday, March 7th, 2023

### New ✨

- GitKraken Insights:
  - Sparkline graphs will now show the shape and trends of `GitKraken Insights` for each metric. 
- Focus View Updates:
  - View, checkout, and start a branch from an issue in the <kbd>My Issues</kbd> section of the Focus View.
  - You may now hide entire sections for Focus View in Workspaces. Customize away!
- Issue View for Workspaces:
  - Added ability to open the issue panel for Workspace issues.

### Improvements 🙌
- Updated Azure Devops integration page with “Work Items” scope.
- Added a new UI setting for hiding the workspace tab when the tab is closed.
- Upgraded to Electron 21.
- Improved stability for font loading.
- Updated font selection settings to present monospace fonts accurately.


### Bug Fixes 🐛
- Disconnecting GitLab Insights integration will no longer affect the connection status for other Insights integrations. 
- Fixed several bugs with keyboard shortcuts in the Interactive Rebase view.
- GitKraken Insights will now successfully connect for Cloud Workspaces connected to Azure DevOps. 


***

<a id="v9-1-1"></a>
## Version 9.1.1

_“9.1.1, what's your emergency?”_

### Tuesday, February 14th, 2023

### Bug Fixes 🐛

- Updated OpenSSL to 1.1.1t, which includes important security updates. 
- Fixed file contents not loading when opening diffs/merges in external tools.

***
<a id="v9-1-0"></a>
## Version 9.1.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ZJCxngwraV4" frameborder="0" allowfullscreen></iframe>
</div>

_“You spoke. We listened.”_

### Tuesday, February 7th, 2023

### New ✨

- [Improved WSL 2 support](/gitkraken-client/current/#improved-wsl-2-support) for the Linux version of GitKraken Client.
 - Users may now install GitKraken Client in a WSL 2 distribution with WSLg and work with their Linux repos.
  - For the best experience, we recommend users also install GitKraken Client on their Windows machine to work with repos hosted outside their WSLg distribution. 
  - For installation or upgrade instructions, check out the [WSL 2 Help Center documentation](https://help.gitkraken.com/gitkraken-client/windows-subsystem-for-linux/).
- [New encoding support](/gitkraken-client/current/#encoding-support) 🎉
  - Configure from <kbd>Preferences > Encoding</kbd> or from the top right of any <kbd>File Diff</kbd> view.
- Users may now [bypass Git Hooks](/gitkraken-client/current/#bypass-git-hooks) when committing after entering a commit message. 
- `GitKraken Insights` is now available for <kbd>Cloud Workspaces</kbd> connected to Azure DevOps.


### Improvements 🙌
- [Amend (rename) stashes](/gitkraken-client/current/#amend-stash-messages):
  - Right-click a stash in the graph and then click <kbd>Edit stash message</kbd>. 
  - Right-click on a stash in the Left Panel to access <kbd>Edit stash message</kbd>.
  - Click the stash message in the Commit Panel to edit the stash message. 
- [Workspace improvements](/gitkraken-client/current/#workspace-improvements):
  - Workspace columns can now be sorted on Repositories, Issues, Pull Requests and WIP tables. 
  - All `GitKraken Insights` metrics now have a dropdown for changing the time period between 7 days or 14 days for licensed users.
- From the <kbd>Interactive Rebase</kbd> editor, the first commit can now be set `Drop`. 


### Bug Fixes 🐛
- Fix submodules update being triggered twice during a Pull (rebase), Rebase, cherry-pick, revert commit, reset, checkout, or undo/redo.
- <kbd>Local Workspaces</kbd> may now be edited again while working offline.
- Users will now get a more helpful message when an integration fails to connect due to a problem with SSL certificate verification.
- When amending commit messages, the draggable resize handle will now correctly resize the text box.
- When amending commit/stash messages, the summary-line text input will now be focused automatically.
- Fixed an issue where Jira Server issues would not show up for a Workspace.
- Fixed a timing issue where Shared Workspaces would not show up for Organization owners if the user was not a team member of that Workspace.
- Fixed an issue where manually inputting the token to login with GitHub would not save the token for the Github Provider.
- Fixed a timing issue that caused branches not to show when relaunching the app from a Workspace.

### Improved WSL 2 Support

We’ve heard that WSL is an essential part of many of our users’ development setup, and as WSL's popularity continues to grow, we’re excited to start offering some improvements for users working in this environment. To give users an opportunity to have a more native-like experience as quickly as possible, we’ve improved the Linux version of GitKraken Client to fix common issues when operating within a WSL 2 environment.

With 9.1, users may now install GitKraken Client in a WSL 2 distribution with WSLg and better work with their Linux repos. For the best experience, we recommend users install GitKraken Client both on their Windows machine as well as their WSLg Linux distro. This allows users to quickly swap between GitKraken Client on each of their operating systems. 

<img src="/wp-content/uploads/wsl-2.png" class="img-responsive center img-bordered">

For more information about WSL 2 / WSLg, and the additional features we’ve introduced to better manage GitKraken Client in this environment, check out the [Help Center documentation](https://help.gitkraken.com/gitkraken-client/windows-subsystem-for-linux/).

### Workspace Improvements

Workspace columns can be sorted on Repositories, Issues, Pull Requests and WIP tables. This should help you better organize your Focus View or Team View. 

<img src="/wp-content/uploads/sort-columns.gif" class="img-responsive center img-bordered">

GitKraken Insights is now available for Cloud Workspaces connected to Azure DevOps, which should help Azure DevOps users measure how fast pull requests get merged.

<img src="/wp-content/uploads/insights-azure2.png" class="img-responsive center img-bordered">

And all GitKraken Insights metrics now have a dropdown for changing the time period between a 7 day or 14 day time period for licensed users.

<img src="/wp-content/uploads/insights-toggle.png" class="img-responsive center img-bordered">

### Quality of Life Boosts

#### Amend Stash Messages

Users may now amend stash messages which should make renaming stashes a breeze. Just right-click a stash in the graph and then click “Edit stash message.” 

<img src="/wp-content/uploads/amend-stash-graph2.png" class="img-responsive center img-bordered">

You may also right click on a stash in the Left Panel to access the same option.

#### Bypass Git Hooks

Another request from users — you may now bypass Git Hooks when committing. To bypass, first stage changes in a repo with Git Hooks enabled and then start typing your commit message. 

<img src="/wp-content/uploads/bypass2.png" class="img-responsive center img-bordered">

You may then click this split button option to commit and bypass the Git Hook.

#### Encoding Support

GitKraken Client 9.1 comes with new encoding support for ISO-8859-1, Windows-1252, and many more. To update the encoding for the app’s File Diff view, navigate to Preferences > Encoding and set your encoding selection for the repository.

<img src="/wp-content/uploads/encoding-preferences2.png" class="img-responsive center img-bordered">

Alternatively, from any file diff in GitKraken Client, click this dropdown menu in the top right to change your encoding preference.

<img src="/wp-content/uploads/file-encoding-diff2.png" class="img-responsive center img-bordered">

Of the two options, we recommend users to change the default encoding in their Preferences. That way you’ll be able to read all diffs with the correct characters.

#### Interactive Rebase “Drop”

And finally, when setting up an Interactive Rebase, you may now set the first commit to `Drop`. 

<img src="/wp-content/uploads/interactive-rebase-drop.png" class="img-responsive center img-bordered">

***
<a id="v9-0-1"></a>
## Version 9.0.1

_“The only thing more constant than software bugs, is the need to fix them.”_ 

### Wednesday, January 4th, 2023

### Improvements 🙌

- The `Open repo` command in the Command Palette will now show repos from deep linking and Local Workspaces. 

### Bug Fixes 🐛
- Fixed a bug on MacOS where having the UI theme set to `Sync with system` caused high CPU usage.
- Workspaces:
  - Issues will now load in Workspace when using GitHub Issues or GitLab Issues. 
  - GitKraken Insights metrics section will still show even if there are no open PRs. 
  - Fixed blank Workspace tab that would show after upgrading to 9.0. 
- Fixed issue saving token when a user manually enters the token to login with GitHub.
- Submodules:
  - Fixed error when discarding all changes after adding a submodule.
  - Fixed submodule not initializing after renaming a submodule. 
  - Fixed submodule not initializing when discarding all changes with submodule changes. 
- Fixed performance hit when undoing `Discard all changes` with LFS files.
- Fixed lag when resizing the commit message. 


***
<a id="v9-0-0"></a>
## Version 9.0.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/gy-lwoVAFCg" frameborder="0" allowfullscreen></iframe>
</div>

### Tuesday, December 13th, 2022

_“Ready to tear into presents? Santa’s “Workspace” has been coding around-the-clock to release these gifts 🎁”_

We know how tedious it can be to figure out what repos have recent WIPs and which repos to open next. That's why we're so excited to present GitKraken Client 9.0, and transform your development workflow.

This version helps you create a hub for all your repos and makes working with multiple repos a breeze. Plus, with features like Workspaces and GitKraken Insights, you'll be able to improve your development productivity in no time.

### New 
- Workspaces ✨
  - There are now two types of GitKraken Workspaces: *Local* and *Cloud*.
    - [Local Workspaces](/gitkraken-client/current/#local-workspaces) are a new type of Workspace that reference only repositories on your machine.
        - Select individual repositories, a directory of repositories, or a `VS Code Workspace` (`.code-workspace`) to create a <kbd>Local Workspace</kbd>.
        - <kbd>Local Workspaces</kbd> can also be created from existing `Project Directories` in the <kbd>Repository Management</kbd> view.
        - Quickly open repositories in a <kbd>Repo Tab</kbd>, or in a `VS Code Workspace`.
        - View the currently checked out branch, remote status, and work in progress across all repositories in the Workspace.
        - View repository details, including the README for each repository in the Workspace.
        - Fetch all repositories in a Workspace at once.
  - [Cloud Workspaces](/gitkraken-client/current/#cloud-workspaces) (previously _Personal_ and _Shared_) are enhanced with Pull Requests and Issues from hosting and issue tracking services.
        - <kbd>Cloud Workspaces</kbd> can be easily created from <kbd>Local Workspaces</kbd> from the Workspace menu.
        - The _Overview_ is now out of _Preview_ and has been renamed to the _Focus View_. It displays Pull Requests, Issues, and work in progress that are relevant to you.
        - The _Team Overview_ is now out of _Preview_ and has been renamed to the _Team View_. It displays Pull Requests and Issues for everyone on your team.
        - Tables inside the _Focus View_ and _Team View_ can now be customized to toggle specific columns on/off.
    - Repositories can now be marked as favorites within all Workspaces.

- [GitKraken Insights - Preview](/gitkraken-client/current/#gitkraken-insights) ✨
    - `GitKraken Insights` measures how fast pull requests are merged into your repositories and more! Get metrics like:
        - Average Cycle Time: Measures the average time it takes for a pull request to be merged for the selected timeframe.
        - Average Throughput: Measures the average number of pull requests merged for the selected timeframe. 
        - Merge Rate: The percentage of merged pull requests compared to open pull requests for the selected timeframe. 
        - Open: The total number of pull requests opened for the selected timeframe.
        - Merged:The total number of pull requests merged for the selected timeframe.
    - Note: GitKraken Insights will be gradually rolled out to all users. Look for it soon! 
- [Ghost branches](/gitkraken-client/current/#ghost-branches) 👻
  - A “ghost” branch is now displayed when hovering over commits in the graph that shows the closest branch in the <kbd>BRANCH / TAG</kbd> column. This can be toggled on/off in <kbd>Preferences > UI Customization</kbd>.
- [Commit highlighting](/gitkraken-client/current/#commit-highlighting) 💡
  - Now when you hover over a branch/tag, the associated commits will be highlighted on the graph after a brief delay. This can be toggled on/off in <kbd>Preferences > UI Customization</kbd>.
- Solo from the graph 🔍
  - You can now solo branches directly from the context menu of branches in the graph, which hides all other branches and commits.


### Improvements 🙌

- Workspaces 🗂
  - The `Create Workspace` form has been refined to include Local and Cloud Workspace types and to make sharing and adding repositories easier.
  - The Workspace loading spinner is less-boring 🍭
  - Improved speed at which _Focus View_ and _Team View_ start to load.
- Left Panel ⬅️
  - Resizing sections in the Left Panel now behaves better in edge cases, like pushing several sections at once. 
  - Sections in the Left Panel can now be maximized via context menu to collapse all other sections.
  - Icons and text in the Left Panel have been aligned and have consistent indents in all sections.
  - The resize handle for adjusting Left Panel width is now centered on the panel edge.
- UI / Themes 🎨
  - The UI has been refreshed in most views to reduce visual noise. This mostly involved reducing the dependency on background colors to separate sections of content and will be noticeable in custom themes.
  - Color values in default Light themes have been updated to be generally brighter.
  - Color values in the Dark (High Contrast) theme have been updated to better separate content after the UI refresh.
  - Menu bar and context menus will now match the GitKraken Client theme in Windows.
- The Mac application icon has been updated to match current Apple guidelines.
- Windows and Linux application icons have also been refreshed.
- Improved LFS performance for cherry-picking or reverting a commit with a large amount of LFS files.


### Bug Fixes 🐛
- Fixed an issue where submodules were left uninitialized (even with 'Keep submodules up to date' enabled in the preferences) after the following actions:
  - Undo or redo a `checkout` or `reset hard` 
  - Cherry-pick, revert, rebase, interactive rebase, reset, pull
- Fixed some theme-ability issues on the toolbar and the New Tab.
- Fixed an issue with false positives in private repo detection.
- Fixed an error that will occur when <kbd>Ctrl/Shift</kbd> clicking within the Left Panel.


### Workspaces

#### Local Workspaces

GitKraken Client 9.0 brings a whole new way to organize your repos. Users may now create <kbd>Local Workspaces</kbd> to group repositories on your machine. 

<img src="/wp-content/uploads/Local-Workspaces-Example.png" class="img-responsive center img-bordered">

To create a Local Workspace, navigate to the Workspace tab in the upper left of GitKraken Client and click on New Workspace.

<img src="/wp-content/uploads/create-local-workspace.gif" class="img-responsive center img-bordered">

Select <kbd>Local Workspace</kbd> and then name your Workspace, and browse to select repos to add to your <kbd>Local Workspace</kbd>.

<img src="/wp-content/uploads/create-local-workspace-3.png" class="img-responsive center img-bordered">

Once your Local Workspace is created, you’ll see all your repos grouped together and get the following benefits:

- View currently checked out branch for each repo.
- Click on any repo name to open it as a tab in GitKraken Client. 
- Multi-select repos to:
    - Perform a fetch for the selected repos
    - Open repos as tabs in GitKraken Client
    - Use your selection to create a Cloud Workspace (formerly called _Personal_ or _Team Workspace_)

That’s right! You can also use your Local Workspace to create a Cloud Workspace, which will enable more visibility into your pull requests, issues, and share your Workspace with teams.

<img src="/wp-content/uploads/Create-cloud-workspace-2.png" class="img-responsive center img-bordered">

#### Cloud Workspaces

Formerly known as _Personal_ and _Shared_ Workspaces, Cloud Workspaces are useful for sharing your Workspace with teams along with enabling GitKraken Insights. 

##### Focus View & Team View

The _Focus View_, which was previously called the _Overview_, is now out of _Preview_ and provides a list of all Pull Requests, Issues, Works in Progress that matter to you. 

<img src="/wp-content/uploads/Focus-View.png" class="img-responsive center img-bordered">

With this release, you may now toggle columns on or off from this gear in the top left corner. 

<img src="/wp-content/uploads/configure-focus-view.png" class="img-responsive center img-bordered">

The _Team Overview_ is also out of _Preview_ and is now called _Team View_. It  will show you all pull requests and issues associated with the repos in your Workspace. 

And similar to the _Focus View_,  you may now toggle columns on or off from this gear in the top left corner. 

### GitKraken Insights

Next, we’re excited to introduce `GitKraken Insights` – which measures how fast pull requests are merged into your repositories. 

<img src="/wp-content/uploads/Insights.png" class="img-responsive center img-bordered">

But why does it matter if you track metrics like pull request Cycle Time and Throughput?

_“I think an underlying principle that exists is that the longer your code stays away from being merged, the more complicated your workflow is going to become.And so as those changes land and your PR and your change becomes more behind from the main trunk branch, the more likely it becomes you will have to do more work to get that code working again.”_
 - Jeff Schinella, Director of Product


To enable `GitKraken Insights`, you’ll first need to open a <kbd>Cloud Workspace</kbd> and then navigate to the Pull Request section. From here, click to connect to your remote hosting service.

<img src="/wp-content/uploads/Connect-Insights.png" class="img-responsive center img-bordered">

Once the connection is complete, return to the Pull Request section in your <kbd>Cloud Workspace</kbd> to view the following metrics for your Workspace pull requests:

- Average Cycle Time: Measures the average time it takes for a pull request to be merged for the selected timeframe.
- Average Throughput: Measures the average number of pull requests merged for the selected timeframe. 
- Merge Rate: The percentage of merged pull requests compared to open pull requests for the selected timeframe. 
- Open: The total number of pull requests opened for the selected timeframe.
- Merged: The total number of pull requests merged for the selected timeframe.


`GitKraken Insights` is currently in _Preview_, and we’d love to hear your feedback.

### UI/UX Refresh

Next, we recently released the Commit Graph for GitLens where we learned how to improve the graph even more. We’re delighted to bring those learnings to GitKraken Client 9.0.

##### Ghost Branches

In GitKraken Client, you will now see a “Ghost” branch when you hover over a commit. This will show the closest branch that contains that commit. The “Ghost” branch will also show when a commit is selected, and double-clicking that ghost branch will checkout the head of the referenced branch.

<img src="/wp-content/uploads/ghost.gif" class="img-responsive center img-bordered">

Users may toggle this setting on or off from <kbd>Preferences > UI Customization</kbd>. 

##### Commit highlighting

When you hover over a branch, the app will highlight all commits referenced by that branch.

<img src="/wp-content/uploads/Commit-highlight.png" class="img-responsive center img-bordered">

Users may toggle this setting on or off from <kbd>Preferences > UI Customization</kbd>. 