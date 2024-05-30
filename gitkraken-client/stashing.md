---

title: Stash
description: Save your changes for later with stashing in GitKraken Desktop.
taxonomy:
    category: gitkraken-client

---

Let's talk about how to save your changes for later with stashing.

***

<a name="stashing-files"></a>

## Stashing files

Stash your changes by hitting the **Stash** icon in the top toolbar.

<img src='/wp-content/uploads/stash.png' srcset='/wp-content/uploads/stash@2x.png' class='img-bordered img-responsive center'>

Your stash will appear on the graph. If you right click on the stash, you will be given the option to:

* **Apply Stash**: Applies the changes to your WIP and retains stash for reusability
* **Pop Stash**: Applies the changes to your WIP and then deletes your stash
* **Delete Stash**: Annihilates a stash
* **Hide**: Hides the selected stash from the commit graph
* **Hide all stashes**: Hides all stashes from the commit graph
* **Show all stashes**: Shows all stashes on the commit graph

<img src='/wp-content/uploads/stash-options.png' srcset='/wp-content/uploads/stash-options@2x.png' class='img-bordered img-responsive center'>

If you only need to pop your stash, then use the Pop Stash button in the upper toolbar:

<img src='/wp-content/uploads/pop-stash.png' srcset='/wp-content/uploads/pop-stash@2x.png' class='img-bordered img-responsive center'>

<a name="stashing-from-the-left-panel"></a>

### Stashing from the left panel

Your stashes will be available from the left panel for review. The same options to Apply, Pop, Delete, Hide, Hide all, or Show all are present too:

<img src='/wp-content/uploads/stash-left.png' srcset='/wp-content/uploads/stash-left@2x.png' class='img-bordered img-responsive center'>

This is helpful for those times you cannot find your stash on the graph.

<a name="naming-a-stash"></a>

### Naming a stash

To name your stash, type the desired name in the `// WIP` field at the top of the graph.

<img src='/wp-content/uploads/custom-stash-wip.png' srcset='/wp-content/uploads/custom-stash-wip@2x.png' class='img-bordered img-responsive center'>

The stash will now appear in the left panel and the graph with the desired name.

<img src='/wp-content/uploads/custom-stash-panel.png' srcset='/wp-content/uploads/custom-stash-panel@2x.png' class='img-bordered img-responsive center'>

<img src='/wp-content/uploads/custom-stash-graph.png' srcset='/wp-content/uploads/custom-stash-graph@2x.png' class='img-bordered img-responsive center'>

### Partial stash

Sometimes you only need to stash some of the files in your WIP.  

Partial stashing is found in the "staged files" panel. Right-click individual files, or multiple files, and select the “Stash file” option to stash those selected files and have their changes reset.

<img src='/wp-content/uploads/partial-stash.png' class='img-bordered img-responsive center'>

**Apply changes from stash to working directory**

You can also partially apply a stash. When a stash is selected, right click files in the right panel to apply their changes to the working directory.

<img src='/wp-content/uploads/partial-stash-apply.png' class='img-bordered img-responsive center'>

Partial stash tips

* You may name a partial stash by typing into the //WIP node or summary section before creating the stash.
* Select additional files for stashing or applying by holding down the Shift or Control key.
* Applying a file from a stash does not remove the file from the stash – use this to safely explore!

## Stash on the Cloud

While Cloud Patches are great for sharing code with other collaborators, you could consider creating a Cloud Patch as a means of stashing changes.

To create a Cloud Patch, first make changes to your code. Click the WIP node that appears at the top of the graph and then click the "Share" arrow to begin the Cloud Patch creation.

<img src='/wp-content/uploads/gkc-create-cloud-patch.png' class='img-bordered img-responsive center'>

When creating a Cloud Patch, you have the following sharing options:

- `Anyone with the link`: Anyone that has access to the public link will be able to work with the Cloud Patch.

- `Anyone in my org`: Anyone in the GitKraken Organization will be able to work with the Cloud Patch. They will be required to authenticate with a GitKraken account to access it.

- `Only collaborators`: Only users in the GitKraken Organization who have been selected when sharing will be able to work with the Cloud Patch. They will be required to authenticate with a GitKraken account to access it.

Cloud Patches shared with you can be viewed in the Cloud Patches Left Panel section under `Shared with Me`.

<img src='/wp-content/uploads/Cloud-Patch-Permissions.png' class='img-bordered img-responsive center'>

Cloud Patch links can be shared with users to open the Cloud Patch in GitKraken Desktop or GitLens. When a Cloud Patch link is opened, the user will be prompted to open the client, clone or open the repository if not known to GitKraken Desktop, and then select the base branch to apply the patch to. From here, they can simply select `apply patch to <branch>`. 

<img src='/wp-content/uploads/gkc-apply-cloud-patch-example.gif' class='img-bordered img-responsive center'>

To delete a cloud path, right-click it and select `Delete Cloud Patch`.

<img src="/wp-content/uploads/gkc-delete-cloud-patch.png" class="img-bordered img-responsive center">
