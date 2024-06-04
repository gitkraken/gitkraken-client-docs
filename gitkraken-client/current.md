---

title: GitKraken Desktop Release Notes
description: View a history of the new features and fixes in GitKraken Desktop's Version 10.
og_image: /img/GitKrakenClient-Hero.png
taxonomy:
    category: gitkraken-client

---

Behold the evolution of GitKraken Desktop! Find out what&rsquo;s new, what&rsquo;s fixed, or just take a trip down memory lane with a nostalgic swagger, remembering those bugs of yesterday.

<a href="https://www.gitkraken.com/download" target="_blank" class="button button--basic ">Download Current Version Now</a>

Check out our [GitKraken Roadmap](https://www.gitkraken.com/git-client/roadmap) to see what we’re working on.

***

<a id="v10-0-2"></a>
## Version 10.0.2

### Tuesday, June 4th, 2024

### Improvements 🙌
 - Repository Management tab:
   - The search bar will be automatically focused when accessing the Repository Management tab.
   - Custom Workspace icons will now show in the collapsible section header.
   - Your scroll position will be saved when returning to the Repository Management tab.
   - After creating a new Workspace, the Workspace will be expanded and scrolled to automatically.
   - User avatars will show in the section header of any shared Cloud Workspace.
 - Experimental Feature - Git Executable:
   - Added push tag support.

### Bug Fixes 🐛
 - Experimental Feature - Git Executable:
   - Fixed an issue where continuing a rebase would fail after a conflict if the current commit message started with `#`.
 - Fixed an issue where the client would fail to load Bitbucket Server users.

 ***

<a id="v10-0-1"></a>
## Version 10.0.1

_“To err is human; to forgive, divine”_

### Monday, May 20th, 2024

### Improvements ✨
 - Updated Git to 2.44.1.
 - Improved the layout of filtering controls in Launchpad.

### Bug Fixes 🐛
 - Fixed an issue where pull requests from archived repositories would appear in Launchpad.
 - Fixed an issue where GitLab Self-Managed Workspaces would not show any repositories.

***

<a id="v10-0-0"></a>
## Version 10.0.0

_“How many arms does Keif have? Ten-tacles.”_

### Tuesday, May 14th, 2024

### New ✨
 - GitKraken Client is now called GitKraken Desktop
 - Focus View is now called Launchpad

### Improvements 🙌
 - Completely re-built our in-app informational/error message pop-ups ("toasts") to give them a fresh look.
 - Added loading icon to Launchpad issue and pull request panel
 - Show provider icon for Launchpad workspace dropdown. Hide hosting service dropdown when a workspace is selected rather than disabling it
 - Default the Launchpad to open in the pull request sub tab
 - Experimental Feature - Git Executable:
   - Added stage files support
   - Added unstage files support
   - Added stash support
   - Added support for Git Credential Manager on SSH settings
 - The Launchpad sub tab will be remembered when going between different tabs and when the client is restarted
 - The Launchpad search text will be remembered when going between different tabs
 - Now able to search Launchpad items using pull request and issue number
 - Updated Git to 2.44.0 and 2.44.0-windows
 - Update git-lfs to 3.5.1
 - Renamed the Jira Server integration to Jira Data Center as Jira Server has reached end of support
 - Use gpg from bundle if gpg executable is not found on Windows
 - Add ability to suggest changes to Pull Requests via Cloud Patches
 - Show Suggested Changes for a Pull Request in the Pull Request view
 - Add a new Team view within Launchpad that shows all PR's and issues for an integration
 - Organize pullrequests within the Launchpad view into different groups. This is only for Launchpad personal view
 - Add action button to open code suggestions for PR's in Launchpad

### Bug Fixes 🐛
 - Interacting with an expired notification now clears that notification instead of leaving it unread forever
 - Fixed an issue where the Launchpad issue and pull request panel did not span to the top of the page
 - Fixed an issue where the diff editor not showing images when switching between files
 - Fixed an issue where LFS detection was failing with LFS repos having custom LFS hooks
 - Fixed getting "Invalid Version: undefined" when creating a workspace
 - Fixed an issue on windows where closing a terminal would close all terminals in the app
 - Fixed an issue where the Launchpad refresh button would disappear for a moment when selected a workspace to filter by
 - Fixed an issue with cloning LFS repositories with hundreds of LFS files.
 - Experimental Feature - Git Executable:
   - Fixed an issue were commits could be made using the user name and email specified in the global git config file instead of the profile values when they were different
   - Fixed fast-forwarding tags
