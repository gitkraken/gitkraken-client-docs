---

title: Git LFS
description: Learn all about Git LFS within GitKraken Client.
taxonomy:
    category: gitkraken-client

---

## What is Git LFS and how does it work?

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/S03EEusFxoI?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

Git LFS (<s>Legendary Fabled Squid</s> Large File Storage) is a Git extension for storing large binary files.

Git LFS allows the user to track binary files directly or by extension. After the files are tracked, Git LFS manages the files as Git normally would, while Git just maintains a text file with metadata about the binary file.

When viewing the diff of tracked LFS files in GitKraken Client, you will see a versioned URL, a generated SHA, and a size pertaining to the size of the original contents of the file:

<img src='/wp-content/uploads/lfs-ref.png' srcset='/wp-content/uploads/lfs-ref@2x.png 2x' class='img-responsive center img-bordered' />

Git LFS stores the binary file content on a custom server or via GitHub, GitLab, or BitBucket’s built-in LFS storage. To find the binary content's location, look in your repository’s `.git/lfs/objects` folder.

Git LFS uses a special Git Hook to handle pushing your LFS files to the special LFS location. Because LFS uses Git filters for handling diffs and proper storage, make sure Git Hooks can run on your machine.

When pulling or checking out a new branch, all files run through a smudge filter. The smudge filter puts a file into your working directory.

LFS reads the SHA stored in Git, then uses that to find the appropriate binary file in the `.git/lfs/objects` folder. If it does not find the file it needs, it attempts to download the file from the LFS server found in the local repository’s git config file.

Once the proper file is found or downloaded, Git LFS replaces the SSH-agent with the binary file in your working directory.

LFS uses the Git clean filter for changes ready for commit and runs when a file is staged. This filter reads the binary content from the file and converts it to a SHA, which will then be stored in Git while the original binary content will be stored in the `.git/lfs/objects` folder.

If you wish to learn more about how Git LFS works with Git, visit the [GitHub repository ](https://github.com/git-lfs/git-lfs) documentation.

***

## Git LFS Requirements

To enable LFS in GitKraken Client, you must first install Git and LFS. The minimum requirements are:

* Git version 2.11+
* LFS version 2.0.1+
* GitKraken Client version 7.0.0+

<div class='callout callout--success'>
    <p><strong>Note:</strong> Usually GitKraken Clientdoes not require Git CLI to perform its operations. However, since we do utilize Git CLI to interact with LFS files you will need to have <a href="https://git-scm.com/" target="_blank">Git installed</a> on your machine if you plan to use LFS. </p>
</div>

### Verify Git and LFS Versions

To verify whether you have the proper version of Git installed, open a terminal or CMD and type the following:
```
git --version
```
You should see something like this:
```
git version 2.13.0
```
On Windows you may see some extra characters appended to the version which is expected. If an error appears, please install (or upgrade) Git on your machine.

GitKraken Client requires version 2.3+ to run LFS. To install or upgrade Git on your machine, visit the [git-scm website](https://git-scm.com/).

Run the following command in terminal or CMD to verify your machine's version of Git LFS:
```
git lfs version
```
You should get output similar to the following:
```
git-lfs/2.1.0 (GitHub; windows 386; go 1.8.1; git bd2c9987)
```
If you do not have Git LFS installed or you have a version less than 2.0.0 installed, visit the [Git LFS website](https://git-lfs.github.com/) to install the proper version.

After both Git and Git LFS are installed, verify that they are on your path either by running the commands above or by checking your path in the terminal.

<div class='callout callout--success'>
    <p><strong>Note:</strong> If GitKraken Client still cannot find Git or Git LFS, the terminal or CMD may be using a different path than the system or user path. For example, on OSX applications launched from the GUI have a different path than those launched from the terminal.</p>
</div>

On OSX and Linux, you can run the following command to see the location of Git LFS on the path:
```
which git-lfs
```
and this command to see the location of Git on the path:
```
which git
```
On Windows Command prompt, use:
```
where git-lfs
```
and:
```
where git
```

*On Windows you can add to your Path Environmental Variable with the following method:*

Search `Env` in the start menu.

<img src="/wp-content/uploads/lfs-AddPathVariable-0.png" class="img-responsive center img-bordered">

Next navigate to `Environmental Variables...` <i class='fa fa-caret-right'></i> Double click **Path** <i class='fa fa-caret-right'></i> Click `New` to add the paths.

<img src="/wp-content/uploads/lfs-AddPathVariable-1.png" srcset="/wp-content/uploads/lfs-AddPathVariable@2x-1.png 2x" class="img-responsive center img-bordered">

<img src="/wp-content/uploads/lfs-AddPathVariable-2.png" srcset="/wp-content/uploads/lfs-AddPathVariable@2x-2.png 2x" class="img-responsive center img-bordered">

<img src="/wp-content/uploads/lfs-AddPathVariable-3.png" srcset="/wp-content/uploads/lfs-AddPathVariable@2x-3.png 2x" class="img-responsive center img-bordered">

You will likely need to add both git and git LFS (LFS can have multiple paths, you would want to add them all).

***

## Initializing LFS on an existing repo

Navigate to your Preferences and you should see the LFS tab in the left panel:

<img src='/wp-content/uploads/lfs-tab.png' srcset='/wp-content/uploads/lfs-tab@2x.png 2x' class='img-responsive center img-bordered' />

<div class='callout callout--warning'>
    <p><strong>Note:</strong> If you do not see the LFS tab, make sure you have a GitKraken Client v3.0.0+ installed and you meet these <a href="/gitkraken-client/git-lfs/#git-lfs-requirements">System Requirements</a>.</p>
</div>

Click to initialize LFS on the repo:

<img src='/wp-content/uploads/init-lfs.png' srcset='/wp-content/uploads/init-lfs@2x.png 2x' class='img-responsive center img-bordered' />

Exit preferences to access two new things: an LFS button in the toolbar and an unstaged change to the `.gitattributes` file that needs to be committed.

<img src='/wp-content/uploads/lfs-toolbar.png' srcset='/wp-content/uploads/lfs-toolbar@2x.png 2x' class='img-responsive center img-bordered' />

Stage and commit the changes to the `.gitattributes` file to finish the LFS initialization.

Existing files need to be untracked from Git and re-tracked to count as LFS files.  Consider removing the files from the repository (Git will think they have been removed/deleted), commit, then re-add the files and re-commit.

The re-added files should now follow your new LFS tracking pattern.

## Initializing LFS on a new repo

When you initialize a new repository, you will have the option to _Initialize with LFS_.

<img src='/wp-content/uploads/init-with-lfs.png' srcset='/wp-content/uploads/init-with-lfs@2x.png 2x' class='img-responsive center img-bordered'/>

## Configuring LFS

Once LFS is initialized on a repository, add tracking patterns to the `.gitattributes` file.  These tracking patterns will tell LFS which files to monitor in your repository.

<img src='/wp-content/uploads/tracking-patterns-lfs.png' srcset='/wp-content/uploads/tracking-patterns-lfs@2x.png 2x' class='img-responsive center img-bordered'/>

Access the `.gitattributes` file by going to <kbd><strong>Preferences > LFS</strong></kbd> or by editing the `.gitattributes` file directly in your text editor.

As another option, add tracking patterns to the repository’s `.gitattributes` file through the Unstage pane in the right panel.

Select the WIP node, right click the file you wish to be tracked by LFS, and select the desired option under LFS.

<img src='/wp-content/uploads/context-menu-lfs.png' srcset='/wp-content/uploads/context-menu-lfs@2x.png 2x' class='img-responsive center img-bordered' />

<div class='callout callout--success'>
    <p>Note: GitKraken Client will automatically perform an LFS pull after cloning a repo or initializing a submodule with LFS </p>
</div>

---

When a file matches a pattern that is being tracked by LFS, an LFS tag appears next to the file name in the right panel.

<img src='/wp-content/uploads/lfs-tag.png' srcset='/wp-content/uploads/lfs-tag@2x.png 2x' class='img-responsive center img-bordered' />

Clicking on the file shows the LFS reference information:

<img src='/wp-content/uploads/lfs-ref.png' srcset='/wp-content/uploads/lfs-ref@2x.png 2x' class='img-responsive center img-bordered'/>

Staging and committing LFS tracked files results in the reference files being saved to your local repo and the actual files being saved to your local LFS cache.

Once your repo is pushed to an LFS-capable remote, the reference files will be saved to the remote repo and the actual files will be pushed to your specified LFS server.

Most LFS actions, such as Checkout, Fetch, Pull, and Push will happen automatically as you use the standard commands in GitKraken Client. However, if you want to use an LFS command in isolation, use the LFS toolbar menu:

 <img src='/wp-content/uploads/lfs-dropdown.png' srcset='/wp-content/uploads/lfs-dropdown@2x.png 2x' class='img-responsive center img-bordered' />

Click the arrow on the button and select the desired command. Other than _Prune_, all of the commands are run by GitKraken Client via the traditional operations.

<div class='callout callout--success'>
    <p><strong>Note:</strong> Pruning is not automatic. Pruning is considered a destructive operation, so be careful about when you run the <em>Prune</em> command. See the <a href="https://github.com/git-lfs/git-lfs/blob/master/docs/man/git-lfs-prune.1.ronn" target="_blank">Git LFS documentation</a> to learn more.</p>
</div>

## LFS FAQ

### I updated to v3.0.0 of GitKraken Client but I cannot find LFS anywhere?

You will need to make sure you have Git v1.8.5 and LFS v2.0.0 installed on your local machine.

### I switched repos and now I do not see the LFS button. Where did it go?

It is most likely that you have switched to a repository that does not have LFS initialized. If you wish to initialize this repo with LFS, you can do so by navigating to the hamburger menu → LFS → Initialize LFS on this repo.

### I added a LFS tracking pattern in GitKraken Client but files with that pattern are not being tracked by LFS, what gives?

Only new files will be tracked by the newly added pattern. If files of the newly added pattern are already being tracked by Git, you will need to untrack them and then re-track them.

The easiest way to do this in GitKraken Client is to remove the files from the repository (Git will think they have been removed/deleted), commit, then re-add the files and re-commit. The re-added files should now follow your new tracking pattern.

### After trying to push my files, I see a prompt requiring my credentials. What credentials is it referring to?

This prompt occurs if your LFS server credentials are not cached. If you are using the same remote hosting service (such as GitHub), then enter the hosting service credentials.

If you are using an internal LFS server (or another LFS service), you will need to enter the credentials for the LFS server.

## Common Pitfalls

### Why is LFS STILL not showing up? 

If LFS is still not appearing as an option in GitKraken Client preferences menu, you may need to add it to your `Path` variable. This can happen if git or git LFS is not installed in the default directory. You should [Verify Git and LFS Versions](/gitkraken-client/git-lfs/#verify-git-and-lfs-versions).

### SSH Keys in GitKraken Client and the CLI
Unlike most features in GitKraken Client, the LFS feature does require git for the CLI as well as LFS. This means that if you are trying to use SSH, your key will need to be configured in your GitKraken Client and for the CLI.

You can automatically generate an SSH Key in GitKraken Client in <kbd><strong>Preferences > SSH</strong></kbd> and save wherever you want locally, or the key will be  in your `~\\.gitkraken\\profiles` folder if you generate from a specific integration. 

You can also use the SSH Agent option to setup and manage your keys, and then tell GitKraken Client to use your agent. [Adding an SSH Key to an SSH Agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) by GitHub

### Using LFS installed using Homebrew on macOS

If LFS was installed using Homebrew, it may not appear in your path. You can run `sudo launchctl config user path "/opt/homebrew/bin:$PATH"` to add homebrew utilities to the PATH for GUI apps. You can see more information on this from the [Homebrew documentation](https://docs.brew.sh/FAQ#my-mac-apps-dont-find-usrlocalbin-utilities).
