---

title: Staging
description: Learn how to stage and review your files before making your commit.
taxonomy:
    category: gitkraken-client

---

When you are working on a project, the staging pane is where changes are prepped for commit.

***

<a name="staging-files"></a>

## Staging files

Staging adds selected file contents to the index, which is like flagging your work as good to go.
To start, select the _//WIP_ node to see all your files on the Commit Panel.

<img src='/wp-content/uploads/WIP-stage.png' srcset='/wp-content/uploads/WIP-stage@2x.png 2x' class='img-bordered img-responsive center'>

Once the //WIP node is selected, a <button class='button button--success button--ui button--nolink'>Stage File</span></button> will appear when you hover over a file in the Commit Panel.

<img src='/wp-content/uploads/stage-file.png' srcset='/wp-content/uploads/stage-file@2x.png 2x' class='img-bordered img-responsive center'>

You may also click on a file for review in the diff or click the <button class='button button--success button--ui button--nolink'>Stage all changes</span></button>. To stage specific lines, select the file, highlight the target lines, then right-click to access the <em>Stage selected lines</em> option.

<img src='/wp-content/uploads/stage-selected.png' srcset='/wp-content/uploads/stage-selected.png 2x' class='img-bordered img-responsive center'>

<div class='callout callout--success'>
    <p>For quickly staging changes, checkout the available <a href="/start-here/keyboard-shortcuts#staging">Staging keyboard shortcuts</a> on hand!</p>
</div>

From here you should be set to  <a href="/gitkraken-client/commits">commit</a>!

<a name="unstaging"></a>

### Unstaging

Unstage files by selecting a staged file and hitting the <button class='button button--danger button--ui button--nolink'>Unstage File</span></button> button that appears. If you click on a file to view the diff, you can selectively unstage lines or hunks.

<img src='/wp-content/uploads/unstage.png' srcset='/wp-content/uploads/unstage@2x.png 2x' class='img-bordered img-responsive center'>

If you need to unstage all files, use the <button class='button button--danger button--ui button--nolink'>Unstage all changes</button> button just above the Staged Files section. From here you should be set to <a href="/gitkraken-client/commits">commit</a>!

***

<a name="discarding-files"></a>

## Discarding files

As you review your files, you may meticulously stage lines or hunks of changes or discard changes.

<img src='/wp-content/uploads/discard-line-hunk.gif' srcset='/wp-content/uploads/discard-line-hunk@2x.gif' class='img-bordered img-responsive center'>

To discard changes, select the _//WIP_ node to summon the <i class="fa fa-trash-o" aria-hidden="true"></i> icon. This option will discard all changes or discard any multi-selected files.

<img src='/wp-content/uploads/discard.png' srcset='/wp-content/uploads/discard@2x.png 2x' class='img-bordered img-responsive center'>

If more than one changes needs to be discard, multi-select files to **multi-discard**.

<img src='/wp-content/uploads/multi-discard.png' srcset='/wp-content/uploads/multi-discard@2x.png 2x' class='img-bordered img-responsive center'>

Next, you may discard hunks of changes from the  <a href="/gitkraken-client/diff">diff</a> of any file.

<img src='/wp-content/uploads/discard-hunk.png' srcset='/wp-content/uploads/discard-hunk@2x.png 2x' class='img-bordered img-responsive center'>

Alternatively in the staging panel, `Discard Changes` is available in the context menu by right-click.

***

<a name="ignoring-files"></a>

## Ignoring Files

You can use the `.gitignore` file to tell GitKraken Client to ignore files in your repo that you don't want to be tracked.  

You can view the `.gitignore` documentation for rules and formatting on the  <a href="https://git-scm.com/docs/gitignore">git-scm website</a>.

To ignore a file, right click on the file in the commit panel and select Ignore.

<img src='/wp-content/uploads/ignore-file.png' srcset='/wp-content/uploads/ignore-file@2x.png 2x' class='img-bordered img-responsive center'>

From this menu you may choose to ignore:
 * The specific file selected
 * All files with that same file extension
 * All files in that same directory 

GitKraken Client will create the `.gitignore` file (unless one already exists) at the root of your repo directory and add the appropriate entry, based on your ignore selection.  

<div class='callout callout--note'>
    <p><strong>Note:</strong> GitKraken Client will only look at the <code>.gitignore</code> located at the root of your repo directory.  Nested .gitignore files are not parsed.</p>
</div>

<a name="ignoring-previously-tracked-files"></a>

### Ignoring previously tracked files

If a file was previously committed to your repo, then you will see the following options when you attempt to ignore it:

<img src='/wp-content/uploads/ignore-options.png' srcset='/wp-content/uploads/ignore-options@2x.png 2x' class='img-bordered img-responsive center'>

Selecting `Ignore` will add the corresponding entry to the .gitignore file, but the changes will not be ignored, because the file is already being tracked by git. 

<img src='/wp-content/uploads/ignore-only.png' srcset='/wp-content/uploads/ignore-only@2x.png' class='img-bordered img-responsive center'>

Selecting `Ignore and Stop Tracking` will add the corresponding entry to the `.gitignore` file and remove the file from the git index, so git stops tracking it.

<img src='/wp-content/uploads/ignore-untrack.png' srcset='/wp-content/uploads/ignore-untrack@2x.png' class='img-bordered img-responsive center'>