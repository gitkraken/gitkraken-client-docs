---

title: Diff, Patch, Blame, and History 
description: Compare your changes with diffs in GitKraken Desktop. Learn about where to access diffs, file blame, and more.
taxonomy:
    category: gitkraken-client

---

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/-0bn2H63axM?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

Compare changes within GitKraken Desktop _diffs_. Learn where to access _diffs_, and how to access _file history_ or _file blame_.

***

<a id="what-is-a-diff-in-gitkraken"></a>

## What is a diff in GitKraken Desktop?

A diff shows additions and removals from a file. <span style='color: #d90171;'>Red</span> is for lines where content was removed whereas <span style='color: #7bd938;'>green</span> is for new lines added.

<img src='/wp-content/uploads/diff-1.png' srcset='/wp-content/uploads/diff-1@2x.png 3x' class='img-bordered img-responsive center' />

GitKraken Desktop's diff comes included with the following:

- Word diffing
- Syntax highlighting
- File mini-map
- Toggles between Hunk View, Inline View, and Split View
- Arrows to move between change sets

Most importantly, the <button class="button button--primary button--ui button--nolink"><span style="color:#141422;">Edit in working directory</span></button> button allows you to edit this file directly. Learn more about this feature in [Editing Files](/working-with-files/editing-files) section.

***
## Where can I access the diff?

Access the diff of a file from:

* **Staging**: Click on a file
* **Commit node**: With a commit node selected, click on any file

If you have two commits selected, GitKraken Desktop shows the difference between the two commits.

<img src='/wp-content/uploads/two-diffs.png' srcset='/wp-content/uploads/two-diffs@2x.png 2x' class='img-bordered img-responsive center'>

Additionally, select multiple commit rows in the graph using <kbd>Shift</kbd> <kbd>Click</kbd> to show its merged diff:

<img src='/wp-content/uploads/merged-diff.png' srcset='/wp-content/uploads/merged-diff@2x.png 2x' class='img-bordered img-responsive center'>

### Hunk view

Hunk view will show the diff as blocks, without the context of the rest of the file.

<img src='/wp-content/uploads/hunk.png' srcset='/wp-content/uploads/hunk@2x.png 2x' class='img-bordered img-responsive center' />

### Inline view

Inline view will show the diff within the context of the entire file.

<img src='/wp-content/uploads/inline.png' srcset='/wp-content/uploads/inline@2x.png 2x' class='img-bordered img-responsive center' />

### Split view

Split view will show a side by side diff comparing how the file looked before (left), and how it looks after the change (right). Note, you may select deleted lines with your mouse from split view. 

<img src='/wp-content/uploads/split.png' srcset='/wp-content/uploads/split@2x.png 2x' class='img-bordered img-responsive center' />

***

## External diff tools
Configure your preferred external diff tool from <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> General</em>:

<img src="/wp-content/uploads/externaldiff.png" srcset="/wp-content/uploads/externaldiff@2x.png" class="img-bordered img-responsive center">

GitKraken Desktop currently _only supports_ the following diff tools:

- Beyond Compare
- FileMerge
- Kaleidoscope
- KDiff
- Araxis
- P4Merge

If your diff tool from the list above is installed and is not showing up in the dropdown, then look for an option to install command line tools.

<img src='/wp-content/uploads/beyond-compare.png' srcset='/wp-content/uploads/beyond-compare@2x.png 2x' class='img-bordered img-responsive center' />

If you would like to use another diff tool, navigate to <em class="context-menu">Preferences <i class="fa fa-caret-right"></i> General</em> and set the <kbd>Diff Tool</kbd> to _Git Config Default_. Then open your global `.gitconfig` file and add these additional lines to use that diff tool. Here are some examples for each operating system:

#### Mac OS
```
[diff]
    tool = meld
[difftool "meld"]
    cmd = open -a Meld --args \"$LOCAL\" \"$REMOTE\"
```

#### Linux
```
[diff]
  tool = meld
[difftool "meld"]
  cmd = meld \"$LOCAL\" \"$REMOTE\"
```

#### Windows
```
[diff]
  tool = meld
[difftool]
  prompt = false
[difftool "meld"]
  cmd = meld "$LOCAL" "$REMOTE"
```

***
## Diff multiple commits

Use the <kbd>Shift</kbd> or <kbd>Cmd/Ctrl</kbd> key to select multiple commits in the graph.

<img src="/wp-content/uploads/select-commits.gif" srcset="/wp-content/uploads/select-commits.gif" class="img-bordered img-responsive center">

This will produce a combined diff, which lists all files that were added, modified, renamed or deleted between the selected commits in the Commit Panel.

<div class='callout callout--basic'>
    <p><strong>Note:</strong> Are you looking to diff branches? Consider using the <kbd>Cmd/Ctrl</kbd> key to select the head commits of each branch.</p>
</div>

***

## Diff a WIP

When you have a Work in Progress (WIP), you can diff this against any commit or branch by ctrl/command clicking the WIP and then the other desired commit. Alternativley, with your WIP sleected, you can right-click the desired commit or branch and select `compare commit against working directory`.

<img src='/wp-content/uploads/gkc-wip-diff.png' class='img-bordered img-responsive center'>

***

## File Blame and History

_File History_ and _File Blame_ information display in the same view.

To access either option, click to view the file diff and the options will appear in the upper right.

<img src='/wp-content/uploads/access-blame.png' srcset='/wp-content/uploads/access-blame@2x.png 2x' class='img-bordered img-responsive center'>

You may also click on a commit in the graph and then right click a file to access _File History_ or _File Blame_. _File History_ shows that file's commit history on the left.

<img src='/wp-content/uploads/file-history.png' srcset='/wp-content/uploads/file-history@2x.png 2x' class='img-bordered img-responsive center'>

_File Blame_ will color code the commit author of each line or hunk.

<img src='/wp-content/uploads/blame.png' srcset='/wp-content/uploads/blame@2x.png 2x' class='img-bordered img-responsive center'>

Use the top toggle button to switch between <kbd>Diff View</kbd>, which shows the selected commit's changes to the file, and the <kbd>File View</kbd>, which shows the file's state at that commit, including the blame info.

## Patch

A patch, or patchfile, is a file describing changes between 2 files. Patch files can be used to distribute changes that a given user would like to make to a particular revision without codifying it onto a git server. Patches can be created from either a commit(s) or a file(s).

To create a patch from a file, right-click on a file and select `Create patch from file changes`. You will be prompted to name the patch after.

<img src='/wp-content/uploads/create-patch-file.png' srcset='/wp-content/uploads/create-patch-file@2x.png' class='img-bordered img-responsive center'>

To create a patch from a commit, right-click a commit and select `Create patch from commit`. You will be prompted to name the patch after.

<img src='/wp-content/uploads/create-patch-commit.png' srcset='/wp-content/uploads/create-patch-commit@2x.png' class='img-bordered img-responsive center'>

You can also multi-select files or commits by holding ctrl/command or shift and clicking. You can then right-click the selected files or commits to create a patch from the selected.

<img src='/wp-content/uploads/multi-selected-patch-v2.png' srcset='/wp-content/uploads/multi-selected-patch@2x.png' class='img-bordered img-responsive center'>

To apply a patch, use the keyboard shortcut `command/ctrl + Shift + P` or click the <i  class="fa fa-magic" style="transform: rotate(225deg)"></i> in the top right of the UI to bring up the Command Palette. Type “Apply Patch" to summon the “Apply Patch” command, and select it to open your file explorer. 

<img src='/wp-content/uploads/apply-patch.png' srcset='/wp-content/uploads/apply-patch@2x.png' class='img-bordered img-responsive center'>

Select your .patch file to then apply changes to your working directory. 

<img src='/wp-content/uploads/patch-applied.png' srcset='/wp-content/uploads/patch-applied@2x.png' class='img-bordered img-responsive center'>

<div class='callout callout--basic'>
    <p>Note: GitKraken Desktop does not yet support generating patches from binary files. This is a preliminary release with better support coming, and if you have feedback please reach out to our <a href="https://www.gitkraken.com/git-client/contact-support">support team</a>. </p>
</div>