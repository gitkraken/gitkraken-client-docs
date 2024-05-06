---

title: Preferences
description: Customize your GitKraken Client experience to match your tastes!
taxonomy:
    category: gitkraken-client

---

Navigate to <i class="fas fa-cog"></i> <kbd><strong>Preferences</strong></kbd> to customize your GitKraken Client experience. Here are what each of the major sections do.


<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png 2x" class="img-responsive center img-bordered">

*** 

## Organization

This section will actually be labeled with your organization name rather than "Organization".  It shows the members and teams within your organization. Click `switch organization` to swap to another organization.

The Owner and any Admins are able to:

- Change role of members within the organization
- Invite members to the organization and purchase licenses
- Create and manage teams


<div class='callout callout--warning'>
    <p><strong>Note:</strong> the Organization section is only available to users who have a Pro or Enterprise license.
</p>
</div>

## General

### Auto-Fetch

Set the number of minutes between auto-fetches. This value must be between 0 and 60 minutes, and it will fetch all visible remotes for the repository. Setting the value to 0 minutes will disable auto-fetch.

If you’re experiencing issues with performance, consider setting your auto-fetch value to 0 and restarting the application. 
 
### Auto-Prune

Removes any remote-tracking references that no longer exist on the remote.

### Default Branch Name

Set the default name when initializing a new repo. The app defaults to `main`.

### External Merge Tool

This is where you may set your preferred external merge tool. 

- [Supported Merge Tools](/working-with-repositories/branching-and-merging/#external-merge-tools)
 
### External Diff Tool

There is where you may set your preferred external diff tool.

- [Supported Diff Tools](/working-with-commits/diff/#external-diff-tools)

### External Editor

You may open a repo in your preferred external editor program using the [Command Palette](/start-here/command-palette/). Supported editors include:

- VS Code
- Atom
- Sublime
- IntelliJ


### Delete ".orig" files

GitKraken Client will make .orig files during a merge. If turned off, these before and after files will not be automatically deleted. 

### Default Terminal

You may open the current repo folder in terminal by navigating to  <kbd><strong>File > Open Terminal</strong></kbd> or use the keyboard shortcuts <kbd><strong>opt</strong></kbd> + <kbd><strong>T</strong></kbd> (Mac) / <kbd><strong>alt</strong></kbd> + <kbd><strong>T</strong></kbd> (Windows + Linux). 

Set your preferred terminal from this preference option for this action.
 
### Use Custom Terminal Command

Enables the option to specify a custom command to open a terminal window. 

For example, to set up GitKraken Client to open Powershell 7, use the command `start "" "C:\Program Files\PowerShell\7\pwsh.exe" -noexit -command "cd %d"`

### Show All Commits in Graph

Enabling this option will force GitKraken Client to always show all commits in repo. This setting may cause performance issues with large repositories.

### Max Commits in Graph

Set the max number of commits GitKraken Client will show in the graph. Lower counts may help improve performance, and the minimum value is 500 commits.

### Remember tabs

This will remember open tabs when you quit GitKraken Client. This option will also remember what tabs you have open for each profile. 

### Longpaths (Windows Only)

For Windows users, GitKraken Client will respect the `core.longpaths` setting in the global .gitconfig. Adjusting this setting will change `core.longpaths` in your .gitconfig. `core.longpaths` only applies to the files in the working directory, not in the .git directory, to maintain compatibility with Git for Windows.

### AutoCRLF (Windows Only)

For Windows users, GitKraken Client will respect the `core.autocrlf` setting in the global .gitconfig. Adjusting this setting will change `core.autocrlf` in your .gitconfig. Enabling this option auto-converts CRLF line endings into LF when adding a file to index, and vice versa when checking out code onto your file system. For more information check out this [git documentation](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#_core_autocrlf)

### Use extended logging in activity log

Provides more information for the activity log. You may access the activity log from <kbd><strong>Help > Support Logs > Activity Logs</strong></kbd>.

### Forget all Usernames and Passwords

Removes credentials that currently stored by GitKraken Client.

### Share work-in-progress status with my team

Allows other users in your team to see your local work in progress files. This is directly related to the [Teams](/working-with-repositories/teams) feature.

## Profiles

GitKraken Client uses profiles to store your app preferences, current [Tabs](/start-here/interface/#tabs), and Git config information.

[Learn more about Profiles](/start-here/profiles)

## SSH & Integrations

GitKraken Client supports HTTPS and SSH authentication, and provides useful integrations with many Git hosting services. Here's how to get started.

- [General SSH settings](/gitkraken-client/authentication/#ssh)
- [GitHub Integration](/gitkraken-client/github-gitkraken-client/)
- [GitHub Enterprise Server Integration](/gitkraken-client/github-enterprise/)
- [GitLab Integration](/gitkraken-client/gitlab/)
- [GitLab Self-Managed Integration](/gitkraken-client/gitlab-self-hosted/)
- [Bitbucket Integration](/gitkraken-client/bitbucket/)
- [Bitbucket Server Integration](/gitkraken-client/bitbucket-server/)
- [Azure DevOps Integration](/gitkraken-client/visual-studio-team-services/)
- [TFS, AWS CodeCommit, custom service, etc](/gitkraken-client/authentication/)
- [Jira Cloud Integration](/gitkraken-client/jira/)
- [Jira Data Center Integration](/gitkraken-client/jira-data-center/)

## Notifications

GitKraken Client's notification system is designed to tell you about updates, bug fixes, product tips, and more. The following preferences are available:

- Enable Desktop Notifications
- Receive Marketing Notifications
- Receive Help Notifications

<div class='callout callout--basic'>
    <p><strong>Note:</strong> Marketing notifications can only be disabled by Pro users.
</p>
</div>


## UI Customization

The following UI preferences are available:

- [Theme](/start-here/themes)
- Notification location
- Date/Time Locale
- Date/Time Short Format
- Show toolbar icon labels
- Enable spell checking
- Display author initials instead of avatars (Gravatar) 
- Show ghost branch/tag when hovering over or selecting a commit
- Highlight associated rows when hovering over a branch
- Show Workspace breadcrumb in toolbar
- Show GitKraken Boards button in toolbar
- Show GitKraken Timelines in toolbar
- Show commit author in graph
- Show commit date/time in graph
- Show commit sha in graph

### Date/Time Locale and Short Format

Date and Time Locale can be set from the UI Customization to match your system or you can set a custom locale. The Date/Time Short Format will match the Date/Time Locale. However, you can define a custom format as well.

See all formatting options that can be used <a href="https://momentjs.com/docs/#/displaying/format/">here</a>. 

## GPG Preferences

Learn more about how to [configure GPG signing](/git-workflows-and-extensions/commit-signing-with-gpg/#configure-gpg-in-gitkraken) in GitKraken Client.

## Editor Preferences

Customize the following settings for your GitKraken Client editor and diff:

- Font
- Font size
- Tab size
- End of line character
- Syntax highlighting
- Show line numbers
- Word wrap

## Terminal

These settings only effect `Terminal` tabs.

- Font
- Font Size
- Enable Autocomplete Suggestions
- Show Graph Panel by Default
- Terminal Theme
- Default Terminal (Windows only)
 
## Experimental

Activate [Experimental Features](/gitkraken-client/experimental-features.md) and try out ideas that are still being worked on.

- Git Binary: Use Git executable instead of NodeGit Git actions (partially, not all git actions are implemented to Git executable)
- AI Commit Message Generation

## Repo-Specific Preferences

Repo-Specific preferences only apply to the repo currently open in GitKraken Client. The following preferences are repo-specific:

- [Encoding](/gitkraken-client/editing-files/#encoding)
- [Gitflow](/git-workflows-and-extensions/git-flow/)
- [Git Hooks](/working-with-repositories/githooks/)
- [Commit](/working-with-commits/commits/)
- [LFS](/git-workflows-and-extensions/intro-and-requirements/)
- [Issues](/integrations/jira/)
- [Team](/working-with-repositories/team-view)
- [Submodules](/gitkraken-client/submodules/#keep-submodules-up-to-date)

You may configure unique repo-specific settings for each repo.

