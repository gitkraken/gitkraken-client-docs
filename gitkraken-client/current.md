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


