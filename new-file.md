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
