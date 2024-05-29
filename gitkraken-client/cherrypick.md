---

title: Cherry Pick
description: Learn how to get changes from one commit to add it to your current branch.
taxonomy:
    category: gitkraken-client

---

Sometimes you commit to one branch, when you meant to commit to another. Here's how to grab the changes you need.

***
To cherry pick a commit, right click on a commit node and select the Cherrypick Commit option:

<img src='/wp-content/uploads/cherrypick.png' srcset='/wp-content/uploads/cherrypick@2x.png 2x' class='img-bordered img-responsive center'>

The cherry pick action is also available from _Local_ on the left panel.

Here, cherry pick grabs the changes from the commit referenced by the HEAD of that branch, and places them onto the branch currently checked out.

<img src='/wp-content/uploads/cherrypick-left-panel.png' srcset='/wp-content/uploads/cherrypick-left-panel@2x.png 2x' class='img-bordered img-responsive center'>

***
### Additional Learning Git Resources:

<p class="small">
	<a href="https://gitkraken.com/learn/git/tutorials/cherry-pick" target="_blank">Cherry Pick Tutorial</a> | <a href="https://gitkraken.com/learn/git/cherry-pick" target="_blank">Learn Git: What is Cherry Pick?</a></a>
</p>

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
