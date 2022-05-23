---

title: Editing Files
description: Learn how to edit files in GitKraken Client.
taxonomy:
    category: gitkraken-client

---
Learn how to edit files in GitKraken Client.
***

## Editing a file

If you just [created a new file](/working-with-files/adding-and-removing#adding-a-file) in GitKraken Client, then you will automatically be placed into edit mode, so you can start coding right away.

There are several ways to edit an existing file:
 * Right click the file from a previous commit or when `View all files` is enabled and select `Edit file`.

 <img src='/wp-content/uploads/edit-context-menu.png' srcset='/wp-content/uploads/edit-context-menu@2x.png 2x' class='img-bordered img-responsive center'>

 * Use the Edit File subcommand in the Command Palette.  
 Hit <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>P</kbd>, type `Edit File`, hit <kbd>Enter</kbd>, type the name of the file, and hit <kbd>Enter</kbd>.

    <img src='/wp-content/uploads/edit-file-fuzzy.gif' class='img-bordered img-responsive center'>
    
 * Click the <button class='button button--primary button--ui button--nolink'>Edit this file</span></button> from Diff/File View.  
    <img src='/wp-content/uploads/edit-diff.png' srcset='/wp-content/uploads/edit-diff@2x.png 2x' class='img-bordered img-responsive center'>
    <div class='callout callout--success'>
    <p><strong>Note:</strong> If viewing a file on a different branch, the button will say <button class='button button--primary button--ui button--nolink'>Edit in working directory</span></button> and clicking the button will take you to edit mode of the version of that file from your current branch.</p>
    </div>
 

The `editable` tag in the upper right corner, denotes that you can edit the current file.

<img src='/wp-content/uploads/editable.png' srcset='/wp-content/uploads/editable@2x.png 2x' class='img-bordered img-responsive center'>

IntelliSense suggestions are shown based on the extension of the file.

<img src='/wp-content/uploads/intellisense.png' srcset='/wp-content/uploads/intellisense@2x.png 2x' class='img-bordered img-responsive center'>

### Saving edits

The blue dot in the upper right corner indicates unsaved changes. 

<img src='/wp-content/uploads/pending-changes.png' srcset='/wp-content/uploads/pending-changes@2x.png 2x' class='img-bordered img-responsive center'>

To save your changes, hit <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>S</kbd>

To exit the file without saving your changes, hover over the blue dot, click the `X`, and select `Don't Save`.

<img src='/wp-content/uploads/dont-save.gif' class='img-bordered img-responsive center'>

### Staging edits

Clicking the <button class='button button--success button--ui button--nolink'>Stage File</span></button> button with pending changes will give you the options to `Save and stage` or `Stage saved changes only`. 

<img src='/wp-content/uploads/save-stage.png' srcset='/wp-content/uploads/save-stage@2x.png 2x' class='img-bordered img-responsive center'>