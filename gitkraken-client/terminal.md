---

title: Terminal
description: A Git-enhanced terminal experience with GitKraken’s powerful visual Git commit graph
taxonomy:
    category: gitkraken-client

---

Open the Terminal to use Git CLI commands while still viewing the graph.

To get started open up a repository and click the Terminal <i class="fa fa-terminal" aria-hidden="true"></i> button in the toolbar, from the new tab view by clicking <kbd>New Terminal Tab</kbd>, or by searching for "terminal" in the <a href="/working-with-repositories/command-palette">command palette</a>.

<img src="/wp-content/uploads/open-gitkraken-terminal.gif" class="img-responsive center img-bordered">

Open a Terminal:

* From the "New Terminal Tab" button in a New tab
* With `Ctrl/Cmd + T` when inside a Terminal tab
* From the Command Palette (`Ctrl/Cmd + P`)

---

## Terminal Commands

### Git Commands and Auto-complete
Most <a href="https://git-scm.com/" target="_blank">Git</a> commands are supported and will appear in the Terminal's auto-complete suggestions, start typing `git` to see them.  

<img src="/wp-content/uploads/autocomplete-suggestions.png" class="img-responsive center img-bordered">

Auto-complete suggestions will also appear for flags.

<img src="/wp-content/uploads/autocomplete-suggestions-flags.png" class="img-responsive center img-bordered">

<div class='callout callout--warning'>
    <p><strong>Note:</strong> Other auto-complete programs can cause the Terminal auto-complete suggestions to not work. You may need to uninstall or disable these programs before using the Terminal.</p>
</div>

### GK Commands
You can access GitKraken CLI specific commands by typing `gkc`. 

<img src="/wp-content/uploads/autocomplete-suggestions-gk-2.png" class="img-responsive center img-bordered">

As well as suggestions for additional parameters.

<img src="/wp-content/uploads/autocomplete-suggestions-gk-diff-2.png" class="img-responsive center img-bordered">

Different views can be accessed using the `gkc` CLI program in the Terminal:

* `gkc panel`: toggles the visualization panel. Also has parameters to reposition the panel top/bottom/left/right.
* `gkc graph`: shows the graph view. Same behavior as the `gk panel`, but additionally it will return to the graph if you're in a different view, and has subcommands for toggling the graph columns with the keyboard.
* `gkc history` and `gk blame`: opens the history/blame panel for a specific file.
* `gkc diff`: shows changes between commits. If no SHAs are provided, it will use your WIP and HEAD. If only one SHA is provided, it will be compared with HEAD.
* `gkc --help`: shows the list of `gk` commands.

<img src="/wp-content/uploads/terminal-gk-command-example-2.gif" class="img-responsive center img-bordered">

---

### Toolbar

A toolbar above the panel will display the current repo name, branch, tag, and number of changes pending to pull/push. Clicking this toolbar will also toggle the panel on/off.

<img src="/wp-content/uploads/terminal-toolbar-toggle.gif" class="img-responsive center img-bordered">

---

### Terminal Preferences 

Navigate to <kbd><strong>Preferences > Terminal</strong></kbd> to change your Terminal preferences.

<img src="/wp-content/uploads/terminal-preferences.png" class="img-responsive center img-bordered">

#### Setting the default terminal on Mac and Linux

ZSH and Bash are currently supported for Mac and Linux. To switch shells you'll need to set the new shell as default in your operating system settings and restart your computer for auto-complete to continue working as expected.

#### Setting the default terminal on Windows

PowerShell and Bash are currently supported for Windows. To switch shells, adjust the _Default Terminal_ under <em class='context-menu'>Preferences > Terminal</em>.