---

title: GitKraken Client Release Notes
description: View a history of the new features and fixes in GitKraken Client's Version 9.
og_image: /img/GitKrakenClient-Hero.png
taxonomy:
    category: gitkraken-client

---

Behold the evolution of GitKraken Client! Find out what&rsquo;s new, what&rsquo;s fixed, or just take a trip down memory lane with a nostalgic swagger, remembering those bugs of yesterday.

<a href="https://www.gitkraken.com/download" target="_blank" class="button button--basic ">Download Current Version Now</a>

Check out our [GitKraken Roadmap](https://www.gitkraken.com/git-client/roadmap) to see what we’re working on.

***

<a id="v9-12-0"></a>
## Version 9.12.0

_“Lucario, use Focus Blast!”_

### Tuesday, February 13th, 2024

### New ✨
 - The new Focus View has improved to display all of your PRs, Issues, and WIPs.
   - You can access the new Focus View from the new Focus View tab. Note, the Focus View will no longer show within a Cloud Workspace.
   - You can still filter items by Workspace using the Workspace filter dropdown.
- You can now host Cloud Patches on your own dedicated storage for the highest level of security (Requires an Enterprise plan).
   - Your organization's admin can configure a self-managed environment for your Cloud Patches at https://gitkraken.dev/settings/security.
   - When creating a Cloud Patch, GitKraken Client will display a message to confirm it will be securely stored on your organization's storage.

### Improvements 🙌
 - Experimental Feature - Git Executable:
   - Added clone support.
   - Improved stability and performance when authenticating with Git remotes.
 - Updated to Monaco 0.45.0
   - This brings improvements to the file/diff/merge editors.

### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
   - Fixed an issue where relative paths for `core.hooksPath` failed to execute hooks.
   - Fixed an issue where SSH and Git version information was parsed incorrectly.
   - Fixed an issue on Windows where updating the file `known_hosts` was not working for rare cases.
 - Fixed an issue where checking out a branch for a pull request in the Focus View would not fetch the remote before checking the branch out.
 - Fixed an issue on macOS where opening a file in Finder from GitKraken Client could cause Finder to freeze.
 - Fixed an issue where the diff view could disappear after quickly selecting a commit in the Commit Graph using the right arrow key or the mouse.
 - Fixed an issue where repos may not load for GitLab Self-Managed instances with self-signed certificates.


***
<a id="v9-11-1"></a>
## Version 9.11.1

### Wednesday, January 10th, 2024

### New ✨
-  You can now edit link permissions for Cloud Patches after creation.

### Improvements 🙌
- Upgraded to Electron 27.
- Experimental Feature - Git Executable:
    - Friendlier GPG errors
- Experimental Feature - AI Commit Message Generation:
    - You can now select an OpenAI model to use with `gpt-4` support added.
    - You can test whether an OpenAI API key is valid with a button in <kbd>Preferences > Experimental</kbd>.
- Added the ability to customize more date/time formats in <kbd>Preferences > UI Customization > Date/Time</kbd>.

### Bug Fixes 🐛
- Experimental Feature - Git Executable:
    - Fixed an issue where invalid credentials with HTTPS remotes showed an info toast instead of prompting for valid credentials.
    - Fixed a problem on MacOS and Linux where SSH commit signing could only be used with `ssh-keygen`.
- Fixed an issue where the compact `Graph` column in the Commit Graph may not display correctly when moving the horizontal scroll bar using the trackpad.
- Fixed an issue where selecting multiple branches in the left panel was not working on Windows or Linux.
- Fixed an issue where the `Date/Time` column of the Commit Graph was not taking into account the time portion set in <kbd>Preferences > UI Customization > Date/Time Format</kbd>.
- Fixed several issues where resolving a `gitkraken://` link wouldn't cancel properly when the user interrupted locating the relevant repository.
- Fixed an issue where navigating between files in the commit panel with the keyboard didn't work as expected.
- Cloud Patches will no longer fail to create on repositories without a remote.

***

<a id="v9-11-0"></a>
## Version 9.11.0

_"Don't be so tight-fisted with that patch. Or actually, do be?"_ 

### Wednesday, December 13th, 2023

### New ✨
 - Added new actions to Focus View items:
   - Merge pull request
   - Close pull request
   - Update issue status
   - Mark issue as closed
   - Open pull request/issue in the browser
 - Added new ways to share Cloud Patches:
   - You can now set link permissions on your Cloud Patch links to allow access to `Anyone with the link`, `Anyone in my org`, or `Only collaborators`.
   - You can now share Cloud Patches directly with members of your organization by selecting specific users when creating a Cloud Patch.
   - You can now view Cloud Patches shared with you in the Cloud Patches Left Panel section under `Shared with Me`.
 - You can now create Cloud Patches from the Command Palette (<kbd>Ctrl/Cmd+P</kbd>).
 - You can now use the left and right arrow keys (as well as <kbd>h</kbd> and <kbd>l</kbd>) to navigate between a commit in the Commit Graph and the first file in that commit.

### Improvements 🙌
 - Experimental Feature - Git Executable:
   - Added merge support.
   - Add pull support when the selected branch is not active.
   - Added new log level `GIT_SILLY` to get extra info about `git` and `ssh` commands in logs.
 - Added new UI Customization setting in preferences to use generic hosting service icons in `branch/tags`.

### Bug Fixes 🐛
 - The commit message view in the Commit Panel now resizes properly when rebasing.
 - Fixed an issue where SSH signed tags would display the signature in their tooltip.
 - Fixed an issue where pull requests for GitHub Enterprise would not load in Workspaces.
 - Fixed an issue where dragging a Commit Graph label onto a Left Panel branch could present a fast-forward option for the wrong remote.
 - Fixed an issue where you could not scroll horizontally on the Commit Graph using the mouse wheel or the two-finger scroll on a trackpad.
 - Fixed an issue where navigating between commits using the up and down keys did not move the vertical scroll bar if the `branch/tag` column was hidden in the Commit Graph.
 - Fixed an issue where the Commit Graph could display a black region after closing an issue view.
 - Fixed an issue where the Commit Graph would not always take you to the commit when searching.
 - Fixed an issue where grouped `branch/tag` nodes would not expand after losing focus on Windows and Linux.
 - Fixed an issue where synced Azure Workspaces would have duplicate entries in the repositories page.
 - Moved the `branch/tag` icons after their name label in the Commit Graph.
 - Fixed a case where the Focus View was in an infinite loading state if no issue tracker is selected.
 - Fixed an issue where detached heads were displayed in the `TAGS` section instead of the `BRANCH` section of the Left Panel.
 - Fixed an issue where the context menu would not display when dragging a tag into a local branch.
 - Fixed an issue where cloning repos from Workspaces would not work if at least 1 repo failed to fetch data.
 - Fixed flicker on commit selection when holding up/down on the Commit Graph.
 - Improved performance in the Commit Graph when moving between commits using the up/down keys.
 - Fixed an issue where inviting users to an organization would silently fail.
 - Added missing options for `detached head` context menu: `Copy commit sha`, `Solo`, `Hide`, `Create patch` and `Create cloud patch`.
 - Fixed an issue where GitLab Self-Managed Workspaces would not load repos, merge requests, or issues if a repo was deleted.
 - Fixed an issue where some deep links may not be recognized by GitKraken Client.
 - Fixed an issue where patch files containing multi-byte characters could fail to apply.

 ### New actions from Focus View

Focus View is wonderful for reviewing a list of all your pull requests, issues, and WIPs for the repositories in your Workspace. With this release, you may now access actions like "Merge" and "Close" for pull requests, along with options to "Update Status" to update the status field of an issue.

<img src="/wp-content/uploads/Focus-View-Actions.png" class="img-responsive center img-bordered">

 ### Set permissions for Cloud Patches

 Cloud Patches are here to make it easy to share code and quickly get feedback. This release adds permission settings to the Cloud Patch creation process.

<img src="/wp-content/uploads/Cloud-Patch-Permissions.png" class="img-responsive center img-bordered">

 Choose between making the Cloud Patch available to anyone with the link, to people in your GitKraken organization, or to specific collaborators. When you share with a specific collaborator, that person will see the Cloud Patch in the Left Panel when they next open GitKraken Client. 

 <img src="/wp-content/uploads/only-collaborators.png" class="img-responsive center img-bordered">

***

<a id="v9-10-0"></a>
## Version 9.10.0

_"Commit and push code to the wrong branch."_ 😇

### Wednesday, November 8th, 2023

### New ✨
 - Commit and push! Added an option to auto-push on commit.
   - Stage changes and type a commit message to access option for commit and push. 
   - You can set the default behavior of the commit button for each repo under `Preferences -> Commit`
 - You can now snooze a Focus View item for a set duration.

### Improvements 🙌
 - Enabled Cloud Patches by default.
   - You can now easily share your changes with other developers by creating a Cloud Patch from your WIP or from the context menu of any commit. Copy the generated link to share the changes.
   - Added ability to delete Cloud Patches from Left Panel.
   - Toggle feature on or off in Preferences > Experimental.
 - Experimental Feature - Git Executable:
   - Provided more information about SSH supported versions on Windows in Experimental Settings.
   - Added support for _Pull (fast-forward if possible)_ and _Pull (fast-forward only)_.
   - Added cherry-pick support.
 - Focus View improvements:
   - Added a clear button to the Focus View search bar.
   - Added a refresh button to the Focus View.
 - Added a helpful warning when signing with an SSH key, and the configured key is a public key, but the corresponding private key has not been added to the SSH Agent.
 - Added the ability to turn off commit lazy loading on the Commit Graph in Preferences.
 - Added the ability to set how to display commit message descriptions in the Commit Graph. 
 - Added emojis support for commits messages on the Commit Graph.


### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
   - Show info toast to remove user from remote url if integration is used.
   - Fixed a problem with SSH_ASKPASS in Windows 10.
   - Fixed GPG signing with passphrase not working when using installed git version (Windows).
   - Improved PuTTY detection.
 - SSH credentials prompt when not using the Git Executable will now show the SSH key file path, not the remote URL.
 - Improved performance in Commit Graph when opening a repository with thousands of grouped branches / tags.
 - Improved loading time of avatars in the Commit Graph when switching tabs.
 - Fixed an issue where the displayed number of items in the Focus View tabs was incorrect.
 - Fixed an issue where the Commit Graph may display lines incorrectly.
 - Fixed an issue where duplicate WIP items would appear in the Focus View repos with the same local path but different remotes. 
 - Fixed an issue where users on older dpkg versions may not be able to install the debian package.
 - Fixed an issue in Commit Graph when hovering over annotated tag icon, the tag message was not appearing in the tooltip.
 - Fixed an issue that was preventing the drag and drop of soloed and hidden branches with the Commit Graph.
 - Fixed an issue where the prompt to refresh the GitLab token would appear more often than required. 
 - Fixed an issue where Cloud Patch links would not work if the app was closed on macOS.
 - Fixed an issue where the scroll position resets after closing a diff view with the Commit Graph.
 - Fixed an issue with branch check out from the dropdown menu of a grouped branch.
 - Fixed an issue where the Focus View is in a infinite loading state when failing to load pull requests or issues.
 - Fixed an issue with deleting unsaved branch names when scrolling away from the branch name input. 
 
 ### Commit and Push

Need to combine 2 actions in 1 click? As a highly requested feature, we're delighted to share GitKraken Client now offers a "Commit and push" option.

<img src="/wp-content/uploads/commit-and-push.png" class="img-responsive center img-bordered">

The option appears when you stage files, and type a commit message. Then just click the arrow icon to choose "Commit and push." For extra convenience, you can set the commit default setting for a repo by navigating to <kbd>Preferences > Commit > Default commit action</kbd>.

<img src="/wp-content/uploads/commit-and-push-preferences.png" class="img-responsive center img-bordered">


### Cloud Patches

 Traditional coding collaboration relies heavily on pull requests, causing developers to wait which then delays valuable feedback. We're redefining how developers work together, by inviting collaboration earlier in the development cycle.

 Enter Cloud Patches. From any WIP, you will now see a "Share" icon in the Commit Panel. You can either share all changes in your WIP, or share staged changes only. 

<img src="/wp-content/uploads/Cloud-Patches-Creation-2.gif" class="img-responsive center img-bordered">

Once the Cloud Patch is created, you can copy the URL to your clipboard and send that to another collaborator. Any person who clicks the link will have the option to open the Cloud Patch in either GitKraken Client or GitLens. Then they can choose whether or not to immediately commit the patch, or add it to their WIP. 

<img src="/wp-content/uploads/Click-Cloud-Patch-URL-2.gif" class="img-responsive center img-bordered">

Cloud Patches are listed in the Left Panel, and you may re-apply or delete patches from here. 

<img src="/wp-content/uploads/Delete-Cloud-Patches.png" class="img-responsive center img-bordered">

With Cloud Patches, you can engage in meaningful discussions and collaborate long before creating a pull request. We believe this promotes early feedback and smooth review processes.
 
***
<a id="v9-9-2"></a>
## Version 9.9.2

_“null is like the absence of color on a computer monitor, a black hole in space, an empty room, or a silent scream.”_ 👻

### Friday, October 13th, 2023

### Improvements 🙌
 - Upgraded to Electron 22.3.25.

### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
   - Fixed "Cannot read properties of null (reading 'startsWith')" due to error reading gpg key from settings.

***

<a id="v9-9-1"></a>
## Version 9.9.1

_“Don't put all your bits in one bucket.”_

### Friday, October 6th, 2023

### Bug Fixes 🐛
 - Fixed an issue where the improved commit graph could not display Bitbucket Server repositories

***

<a id="v9-9-0"></a>
## Version 9.9.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/8J-YLeIYIWs" frameborder="0" allowfullscreen></iframe>
</div>

_“Let's finally pin down that cloud.”_

### Tuesday, October 3rd, 2023

### New ✨

- Experimental Feature - Cloud Patches:
  - Share your work with others by creating a Cloud Patch from any WIP node.
  - Select a WIP to access "Share all files as cloud patch" button in the Commit Panel.
  - Create a Cloud Patch from staged changes.
  - Apply a Cloud Patch by following a Cloud Patch URL to open in GitKraken Client and then review the contents in the Commit Panel.
  - Cloud Patches are organized in the Left Panel, where you may re-apply a patch to your working directory or re-copy the URL.
- Focus View now supports pinning and snoozing for PRs and ISSUES.
- Experimental Feature - New Commit Graph:
  - Added "Compact Graph Column" option from Commit Graph settings gear.
  - Drag and drop to reorder columns.
  - Added inline commit descriptions.
  - Improved performance when resizing the app window.
  - This feature will be defaulted on for all users.


### Improvements 🙌
 - Experimental Feature - Git Executable:
   - Added revert commit support.
   - Added pageant ssh agent support.
 - Focus View now displays an issues status.


### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
   - Fixed an issue where the commit graph would fail to load in some cases.
   - Conflicting git config `fetch.pruneTags` will only be allowed for the main remote.
   - Fixed a problem with remote actions when a non-standard SSH port was used.
   - Fixed a problem in Git Executable with known_hosts file on Windows.
   - Commit signing with SSH can now use a different SSH key than the one used for credentials.
 - Fixed an issue where the commit message viewer did not change its height when clicked.
 - Fixed a missing option to remove a repo for Azure Workspaces whose repos were manually added.
 - Fixed an issue where locating an Azure repo in a Workspace did not save its location.
 - Fixed a bug where GitLab issue descriptions would disappear when clicking the edit button in the issue view panel.
 - Fixed an issue where some macOS icon sizes would look distorted.
 - When immediately committing a cherry-pick or revert:
   - If there is a conflict, hooks will not be executed.
   - If there are no changes, no empty commit will be generated.
 - Fixed an issue where repositories could not be deleted on Windows.
 - Fixed an issue where the incorrect date/time format would sometimes display in the settings UI.
 - Fixed an issue where the incorrect locale would sometimes be used for date/time formatting.
 - Removed unnecessary scroll bars around the commit message field.
 - Fixed the following issues with `gitkraken://` deep links:
   - Fixed an issue where opening a deep link would prompt users to select a repo even if one of those repos is the active tab.
   - Partially fixed an issue where opening a deep link would prompt users to select a repo, but only offer slightly-rephrased versions of the same file path. (Some issues are still known with regards to letter casing on Windows, and uncommon file paths.)
 - Focus View no longer loads Jira Issues set to Done.

***
<a id="v9-8-2"></a>
## Version 9.8.2

_"How many upgrades until Electron becomes a Proton?"_

### Friday, September 15th, 2023

### Bug Fixes 🐛
- Upgraded to Electron 22.3.24.

***

<a id="v9-8-1"></a>
## Version 9.8.1

_“The graph-ity of these bugs demanded a hotfix!”_

### Wednesday, September 6th, 2023

### Bug Fixes 🐛
- Fixed a bug where double-clicking a branch in the Left Panel was not checking out the branch.
- Fixed a bug where graph columns could not be resized.
- Fixed a bug where filtering by author was not working in the graph.

***

<a id="v9-8-0"></a>
## Version 9.8.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/BnYk4XmoLTc" frameborder="0" allowfullscreen></iframe>
</div>

_“Because context switching is why you forget things.”_

### Tuesday, September 5th, 2023

### New ✨
 - The Focus View has been improved!
   - Pull Requests, Issues and Works in Progress have been combined into a single view.
    - We also added buckets for PRs, ISSUES, and WIPS only.
      - Filter PRs by `Mine`, `Created by Me`, `Assigned to Me`, or `Needs my review`.
      - Filter ISSUES by `Mine`, `Created by Me`, `Assigned to Me`, or `Mentioned`.
   - Note: If you're new to Focus View, you may access the Focus View tab from any [Cloud Workspace](https://help.gitkraken.com/gitkraken-client/workspaces/#cloud-workspaces). 

### Improvements 🙌
 - Enhanced 'Invite Users' Modal: Added X button for email removal and improved email display as individual components.

### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
  - Improved handling of ssh_config options, specifically `StrictHostKeyChecking` and `UserKnownHostsFile` and their interaction with remote actions.
 - Fixed Workspace repo list having duplicate entries when an Azure repo is deleted.
 - Fixed a bug where Jira Server issues could not be opened in the browser due to a malformed URL.
 - Fixed cursor jumping to end of input when updating the Date/Time Short Format preference.
 - Fixed the Workspaces tab re-loading data when closing other tabs.

***

<a id="v9-7-1"></a>
## Version 9.7.1

_"How much work could a working directory work if a working directory could work wood?"_

### Tuesday, August 15th, 2023

### Bug Fixes 🐛
- Improved performance when selecting the working directory.


***

<a id="v9-7-0"></a>
## Version 9.7.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/nWt2PK0zQXA" frameborder="0" allowfullscreen></iframe>
</div>

_“Shall we compare dates?”_

### Wednesday, August 9th, 2023

### New ✨
- Your working directory can now be compared against any commit or branch! This can be accomplished in two ways:
    - Right-click a commit or branch, and choose `Compare commit against working directory`
    - Use <kbd>Ctrl</kbd> click (or <kbd>Cmd</kbd> click on MacOS) to select your Work-in-Progress ("WIP") node, along with the commit of your choice.
- GitKraken Client will now attempt to pull Date/Time settings from OS preferences, along with an override in <kbd>Preferences > UI Customization</kbd>.
   - Windows: Region & Short date format preferences
   - macOS: Region & Date format preferences
   - All: LC_ALL & LC_TIME environment variables

### Improvements 🙌
 - Experimental Feature - Git Executable:
   - Added tag support.
   - Added GPG Preferences setting for SSH commit signing. 
 - Added an indicator for repositories in the Workspace `REPOSITORIES` list when multiple paths are detected. Clicking this will allow the user to specify which repository to use.

### Bug Fixes 🐛
 - Fixed an issue where `Pull Requests` were not loading for Bitbucket Workspaces.
 - Improved home directory detection on Windows.
 - App will now create `~/.ssh` directory if it doesn't exist when updating `~/.ssh/known_hosts`.

***
<a id="v9-6-1"></a>
## Version 9.6.1

_“Sharing is caring.”_

### Tuesday, August 1st, 2023

### New ✨
 - Added a share button in the Workspaces tab for inviting organization members and/or teams to join a Workspace.

### Improvements 🙌
 - Upgraded to Electron 22.
 - Experimental Feature - Git Executable:
   - Added push support.
   - Force push will now default to `--force-with-lease`, and prompt to `fetch` or `push --force` (without lease) when the remote ref and remote-tracking branch are different.
   - Added support for streaming Git Hooks output.
 - Renamed the GitKraken Terminal command `gk` to `gkc`.

### Bug Fixes 🐛
 - Fixed an issue loading Workspace pull requests when repos have too many pull requests.
 - Fixed an issue where GitKraken Client couldn't start if the last opened repository was no longer openable.
 - Fixed instances where the Git info in the Workspace repository list would not display.
 - Fixed error toast that appears when a rebase fails due to conflicts.
 - Fixed an issue where GitKraken Client wouldn't show that a merge was active after resolving a conflict.
 - Fixed an issue where Workspace pull requests would not display if a team, bot, or mannequin was a requested reviewer.
 - Fixed an issue where the GPG program could be set to an invalid value, causing issues with GPG actions.
 - Fixed cases of improper UI for the Workspace pull request list when using the search bar.
 - Fixed cases where a blank screen could appear while viewing a repo's README from a Workspace.
 - Fixed tilde resolution of `core.hooksPath` in some cases.

***

<a id="v9-6-0"></a>
## Version 9.6.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/GcKqlqDzFDU" frameborder="0" allowfullscreen></iframe>
</div>


_“Insights get a solo 🎻”_

### Tuesday, July 11th, 2023

### New ✨
 - GitKraken Insights in Workspaces:
   - GitKraken Insights has been moved from the Pull Request page to its own Insights page.
   - Added a "Last updated date" timestamp.
   - Added a refresh button for an easier time updating Insights metrics.
 - Azure DevOps Workspaces:
  - Users may now create a manually managed Azure DevOps Workspace from a Workspace synced with an Azure Project.

### Improvements 🙌
 - Git Executable:
   - The Git Executable feature will now be enabled by default for all GitKraken Client users.
   - Added support for SSH commit signing while using the Git Executable. Commit signing will need to be configured in your gitconfig for now (via `gpg.format`, `user.signingKey`, and `gpg.ssh.allowedSignersFile`). Note that actions that do not currently use the Git Executable (like rebasing) will still use GPG for signing.
   - Added support for SSH strict host key checking.
 - Resize commit messages in the Commit Panel to see more (or less) of the message.
  - First select a commit in the graph to access the resize handle for the commit message in the Commit Panel.
 - Improved performance of `View all files` on large repositories.


### Bug Fixes 🐛
 - Pull request panel will once again auto-populate with the commit message when the pull request contains only one commit.
 - When the experimental "Git Executable" feature is enabled, SSH settings for specific integrations will no longer be overridden by the SSH agent.
 - Cloud Workspaces:
   - Fixed Azure DevOps projects not appearing when creating/editing a Cloud Workspace.
   - Fixed `MENTIONED` and `ASSIGNED TO ME` filters on Azure DevOps Cloud Workspaces.
   - Cloud Workspaces that have already been fetched will no longer disappear when there is an interruption fetching Cloud Workspaces (such as losing connection to the Internet).
   - Fixed an issue of `cannot read properties of null (reading 'match')` when using the Git Executable experimental feature.
   - Failure cases in Workspaces have better error messaging to tell the user what is wrong:
     - ...When GitKraken's integration permissions have been revoked externally (e.g. from the GitHub website).
     - ...When a Jira administrator attempts to view the issues of a private project which they do not have permission to view.
 - Fixed an issue where Local Workspaces were not loading.
 - Fixed issues with adding or viewing Workspaces in the breadcrumbs for repos without a remote.
 - Fixed an issue where Jira issue types were not loaded after selecting a Jira project.
 - Fixed an issue where Cherry Picks / Revert completion messages falsely claimed that, "the current branch already has all changes from the commit."
 - Fixed an issue where button labels were missing when signing in with SSO and more than one provider is available.
 - Fixed an issue where many auto-fetches could queue up in the background.

***

<a id="v9-5-1"></a>
## Version 9.5.1

“Squashed bugs.”

### Monday, June 12th, 2023

### Bug Fixes 🐛
- Fixed an issue where a merge is aborted when there are conflicts and the merging branch is checked out.
- Fixed an issue that would occur when squashing certain commits.

***
<a id="v9-5-0"></a>
## Version 9.5.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/KsF5DLYqIcc" frameborder="0" allowfullscreen></iframe>
</div>

_“How complex can it be?”_

### Wednesday, June 7th, 2023


### On-Premise 🖥

- Git Executable has been enabled for all On-Premise users to allow Git to directly perform actions like fetch, commit, and much more instead of the Nodegit library. 
  - Users may toggle the setting from <kbd>Preferences > Experimental</kbd>. 
- On-Premise and Serverless clients now also benefit from the new first time user experience. 


### New ✨

- Workspaces got a power boost:
  - Invite individuals from your GitKraken Org to a Workspace.
- Pull all repos in a Workspace using the <kbd>Pull all</kbd> button located in the Repositories page.
- ✨ Preview feature:  Added a `Complexity` column to the Workspace Focus View, Team View, and  Pull Requests page:
  - Complexity is a scale of 1 to 4 that scores a pull request’s complexity based on:
    - Number of lines changed
    - Number of files change
    - Number of commits made

### Improvements 🙌
- Git Executable has been enabled for all GitKraken Client users to allow Git to directly perform actions like fetch, commit, and much more instead of the Nodegit library. 
  - Provides performance improvements for fetch, commit, and more. 
  - Users may toggle the setting off or on from <kbd>Preferences > Experimental</kbd>. 
    - Note: This update will be slowly rolled out within the first week of the 9.5 release.
- New user experience improvements:
  - New users may now start with one of their Cloud Workspaces when launching the app for the first time. 
    - When starting with a Cloud Workspace, the Workspace now opens on the Repositories view.
  - During onboarding, users can configure SSH keys for integrations.
  - Improved the URL clone user interface on the new user onboarding.
- Workspace improvements:
  - Added single dropdown to change the time period for all `GitKraken Insights` metrics.
  - Added additional options to locate or clone a repository when checking out a branch or viewing a Pull Request from a Workspace.
  - Updated messaging when opening the Workspace and no integration is connected.
- Improved syntax highlighting and additional language support in the GitHub Pull Request View.
- Added icons in Pull Request View timeline for comments, requested changes, and reviews.
- Added logging for Git commands with GitKraken Client log system.
  - Requires enabling both the “Git Executable” setting from <kbd>Preferences > Experimental</kbd> and the `Use extended logging in activity log` setting from <kbd>Preferences</kbd>.
- Support viewing Git hook output using Git Executable feature.
- Added option to close login modal using the `Esc` key.



### Bug Fixes 🐛
- Fixed case where Git binary wouldn’t fetch from `HTTPS` remotes on older Linux distros (ex. CentOS-7).
- Fixed case where Git binary wouldn’t fetch from `HTTPS` remotes in Snap installs.
- Fixed issue where editing working directory files while multiple commits were selected caused diff display issues for selected commit range.
- Fixed delay with loading spinner appearing. 
- Fixed UI display issue with long emails in the sample commit during the first time user onboarding. 
- Fixed various “unique key prop” errors in Workspaces.
- Azure Issues status now reflects the status options on the main Azure app. 
- Fixed an issue where users were shown an upgrade button in the issue view panel when the issue’s repo is not cloned or located.
- Fixed an issue where the Workspace search bar would disappear.
- Fixed an issue where the Workspace repository page would not load a repo’s ahead/behind data.
- Git binary no longer incorrectly uses bundled SSH instead of system's OpenSSH when `Use Local Agent` setting is enabled.


***
<a id="v9-4-0"></a>
## Version 9.4.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/0EXUm9MI9uo" frameborder="0" allowfullscreen></iframe>
</div>

_“A release for the bold and curious.”_

### Monday, May 8th, 2023

### New ✨

- <kbd>Experimental</kbd> section now available from `Preferences`, and users may now opt-in for:
  - Experiment 1: AI Generated Commit Messages
    - Generate commit messages from any staged changes by connecting with an OpenAI API key. 
  - Experiment 2: Bundled Git Executable
    - GitKraken Client will use Git instead of the Nodegit library for actions like fetch and commits, plus deliver some performance improvements. 
- Refreshed the new-user onboarding, for a smoother experience into the app. 


### Improvements 🙌
- When adding repos to a `Workspace` connected to Azure DevOps, you may now select specific Azure DevOps repos instead of syncing an entire project. 
- Improved position of “traffic light” window controls on MacOS.
- Improved the left panel resize handle UI.

### Bug Fixes 🐛
- Deleting the default branch name setting no longer sets the default branch name to empty string in `.gitconfig`.
- Changing this setting also no longer edits the .gitconfig file at all if the sync `.gitconfig` with profile setting is not checked.
- Basic text-editing context menu has been added to Left Panel filter input.
- Added error toast if the app detects different capitalization in remote URLs.
- Fixed issue retaining selected Jira project or Trello board when changing `Workspaces`.
- Fix duplicate repos in the Local Workspace repo list when the repo was deleted from the users machine.
- Fix error ‘Checkout Failed: stdout maxbuffer length exceeded’ when checking out in some big LFS repos.
- Improved the app’s handling of commits with an empty message.
- Fixed a case where opening a file in an external editor would not complete the action. 



***


<a id="v9-3-0"></a>
## Version 9.3.0

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/UZmwAu-2UYw" frameborder="0" allowfullscreen></iframe>
</div>

_“Wait, Azure is a color?”_

### Thursday, April 6th, 2023

### New ✨

- Azure DevOps Integration Boosts:
  - View and edit Azure Work Items in Workspaces from `Focus View` or `Team View`.
    - Create a branch from an Azure Work Item.
- One-click integration connection from <kbd>Preferences > Integrations > Azure DevOps</kbd> (but you can still use personal access tokens too). 
- Sign into the app with Azure.


### Bug Fixes 🐛
- Fixed an issue where the Workspace issue branch column would not update if a branch for the issue was deleted. 
- Fixed an issue where the Work In Progress table was not working for Azure DevOps Cloud Workspaces.


***

<a id="v9-2-1"></a>
## Version 9.2.1

_“Why did the font go to the doctor? Because it had Type-Face!”_

### Monday, March 13th, 2023

### Bug Fixes 🐛

- Fixed a crash on MacOS that could occur based on the user’s installed fonts.
- Resolved `.build-id` Electron conflict in the RPM package.


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