---

title: Git Hooks
description: Compare your changes with diffs in GitKraken Client. Learn about where to access diffs, file blame, and more.
taxonomy:
    category: gitkraken-client

---

Git hooks are shell scripts that execute after an event such as a commit or push.

In the following video, we will take you through the basics of what a Git hook is and demonstrate how to use one in GitKraken Client.

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ZZgyILr-TjA?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>


***

## Where are Git hooks?

Hooks are stored in the `hooks` subdirectory of the `.git` directory. This folder is automatically created when you initialize a new repository in GitKraken Client and is located in `.git\hooks` in your project directory.

Hooks are unique to your local repository and will not be copied over if you create a new repository. Feel free to add, change, or remove scripts from this folder as necessary.

<img src='/wp-content/uploads/hook_location.png' srcset='/wp-content/uploads/hook_location@2x.png 2x' class='img-responsive center img-bordered' />

If running OSX or Linux, GitKraken Client will seamlessly detect any Git hooks in your repository if your scripts are set to be executable. If you forgot to set your files to executables, GitKraken Client will throw an error as a heads up.

And if running Windows, GitKraken Client will detect your Git hooks automatically.

***

## Define a custom hook path

Users can define a custom path for git hooks by going to <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> Git Hooks</em>. <button class="button button--primary button--ui button--nolink">Browse</button> to the location or enter the path to your git hook folder.

This custom git hook path is defined on a per-repository basis.

<img src='/wp-content/uploads/hook_preferences.png' srcset='/wp-content/uploads/hook_preferences@2x.png 2x' class='img-responsive center img-bordered' />

***

## What hooks are supported by GitKraken Client?

Here are the hooks supported by GitKraken Client. Where appropriate, beneath each hook are the actions during which GitKraken Client calls that hook:

<table class='table table--bordered table--shortcuts'>
  <tbody>
      <tr>
          <td style="width: 35%;"> <h3> <code>pre-commit</code></h3> </td>
          <td style="width: 65%;">
            - Commit
            <br>
            - Amend
            <br>
            - Merge Resolve
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3><code>prepare-commit-msg</code></h3> </td>
          <td style="width: 65%;">
            - Commit
            <br>
            - Amend
            <br>
            - Cherrypick
            <br>
            - Merge
            <br>
            - Squash
            <br>
            - Revert
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>commit-msg</code></h3> </td>
          <td style="width: 65%;">
          - Commit
          <br>
          - Amend
          <br>
          - Merge Resolve
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>post-commit</code></h3> </td>
          <td style="width: 65%;">
          - Commit
          <br>
          - Amend
          <br>
          - Cherrypick
          <br>
          - Merge Resolve
          <br>
          - Revert
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>pre-rebase</code></h3> </td>
          <td style="width: 65%;">
          - Rebase
          <br>
          - Squash
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>post-checkout</code></h3> </td>
          <td style="width: 65%;">
          - Checkout
          <br>
          - Discard Changes (selectively)
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>post-merge</code></h3> </td>
          <td style="width: 65%;">
          - Merge (Without Conflicts)
          <br>
          - Fast-Forward
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>post-rewrite</code></h3> </td>
          <td style="width: 65%;">
          - Amend
          <br>
          - Squash
          <br>
          - Rebase
          </td>
      </tr>
      <tr>
          <td style="width: 35%;"> <h3> <code>pre-push</code></h3> </td>
          <td style="width: 65%;">
          - Push Branch
          <br>
          - Push Tag
          <br>
          - Delete Remote Branch
          <br>
          - Delete Remote Tag
          </td>
      </tr>
  </tbody>
</table>


***
## Git hooks example

Git hooks are scripts that perform automated actions when a specific action is performed in GitKraken Client or the command line. The git hook name usually indicates the hook’s trigger (e.g. pre-commit).

Git hooks live under the .git folder of your repo in a directory called hooks. The path to the hooks will look similar to repo/.git/hooks.
### Tools needed
- GitKraken Client
- Text Editor - I will be using [Visual Studio Code](https://code.visualstudio.com/)
- Terminal - I will be using [iTerm2](https://www.iterm2.com/)

### Hook Purpose
In this example, we'll create a `pre-commit` hook. This hook validates the git config's global user email and checks whether a _gpg key_ exists. The hook is useful so that the commits contain the correct committer email address and also to ensure the commits are signed.

### Creating the git hook

#### Step 1
First navigate to the hooks directory for the target repo. Open a Visual Studio Code window and navigate to <kbd><strong>~/repo/.git/hooks</strong></kbd>. From here, add a new file to the `.git/hooks` directory called `pre-commit`.

<img src='/wp-content/uploads/vscode-to-hooks.png' class='img-responsive center img-bordered' />

<div class='callout callout--warning'>
    <p>Note 📝 - To make the .git folder visible in Visual Studio Code you will need to remove **/.git from files.exclude in the Visual Studio Code settings.</p>
</div>

#### Step 2
Now that we have our pre-commit file, we need to make it executable. To do this we will need the command line.

Open a terminal window by using `option + T` in GitKraken Client. Once the terminal windows is open, change directory to `.git/hooks`.

Then use the command `chmod +x pre-commit` to make the pre-commit file executable.

<img src='/wp-content/uploads/chmod-pre-commit-hook.gif' class='img-responsive center img-bordered' />

<div class='callout callout--warning'>
    <p>Note 📝 - If you do not have your terminal setup in GitKraken Client, please review the <a href="/start-here/tips/#9-open-terminal">Start Here Tips</a> for setup details.</p>
</div>

#### Step 3
Now we create our script using bash. In order for the script to run, we first need to specify our shell. Do this by using `#!/bin/bash` at the beginning of your script for bash or `#!/bin/sh` if using the sh shell. Any script that exits with anything other than exit code 0 is considered a fail.

This `pre-commit` hook watches for incorrect commit authors and unsigned commits using the script below.

**Script variables:**<br>
`PWD` - Print working directory<br>
`globalEmail` - Get email in global git config<br>
`signingKey` - Get key in global git config<br>
`workEmail` - This is your target email address. The email needed to commit successfully.<br>

Now to explore the conditions we have set for our script. First we validate that the working directory contains *demo* and that the global git config user.email matches with our workEmail. If it fails we will see:

```
        echo "Commit email and global git config email differ"
        echo "Global commit email: "$globalEmail""
        echo "Committing email expected: $workEmail"
        exit 1

```

If the condition is met we move on to the next condition. If the global user.signingKey is empty we display:

```
        echo "No signing key found. Check global gitconfig"
        exit 1
```
If the condition is successful the script will run and the commit will be made.

#### Full script
```
#!/bin/bash

PWD=`pwd`
globalEmail=`git config --global --get user.email`
signingKey=`git config --global --get user.signingkey`
workEmail="example@axosoft.com"

if [[ $PWD != "*demo*" && $globalEmail != $workEmail ]];
then
        echo "Commit email and global git config email differ"
        echo "Global commit email: "$globalEmail""
        echo "Committing email expected: $workEmail"
        exit 1
elif [[ $signingKey -eq "" ]];
then
        echo "No signing key found. Check global gitconfig"
        exit 1
else
        echo ""
        exit 0
fi
```

### Git hook in action
<img src='/wp-content/uploads/hook-in-action.gif' class='img-responsive center img-bordered' />

### Bypass git hooks

There may be times when you want to skip your Git hooks when making a commit. This can be done on a commit-by-commit basis by selecting the `Commit and skip hooks` option. 

<img src='/wp-content/uploads/bypass-git-hooks.png' class='img-responsive center img-bordered' />