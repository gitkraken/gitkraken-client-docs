---

title: Squash
description: Squash commits to clean up your graph!
taxonomy:
    category: gitkraken-client

---

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/cr1N8VTRmfM?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

***

Squashing is available for commits that meet the following requirements:

* Selection contains more than one commit
* Genealogically consecutive
* Chronologically consecutive
* The oldest commit in the list has a parent

If all these conditions are met, the Squash option appears when you right click the commit node.

<img src='/wp-content/uploads/squash.gif' srcset='/wp-content/uploads/squash@2x.gif' class='img-bordered img-responsive center'>

Clicking the squashed commit will display the commit message in the right panel.  You can click on the commit message to amend it and consolidate all of the commit messages from your squashed commits.

<img src='/wp-content/uploads/amend-commitmsg.png' srcset='/wp-content/uploads/amend-commitmsg@2x.png' class='img-bordered img-responsive center'>

### Pushing a squashed commit

In general, you should not push commits to your remote that you intend to squash, but what happens if you have already pushed them and you squash locally?  Your local branch has the squashed commit, but your remote branch still has all of the commits.

<img src='/wp-content/uploads/squashed-remote.png' srcset='/wp-content/uploads/squashed-remote@2x.png' class='img-bordered img-responsive center'>

When you push to your remote, you will receive a warning that your current branch is behind the remote branch.  This is expected, because  the HEAD of your current branch is no longer a descendent of the remote branch's HEAD.  

<img src='/wp-content/uploads/squash-pushremote.png' srcset='/wp-content/uploads/squash-pushremote@2x.png' class='img-bordered img-responsive center'>

In this instance, a <button class='button button--danger button--ui button--nolink'>Force Push</button> will allow you to push the squashed commit to your remote and retain the clean history of your local branch.  

<img src='/wp-content/uploads/force-push.png' srcset='/wp-content/uploads/force-push@2x.png' class='img-bordered img-responsive center'>

You will see a warning letting you know that <button class='button button--danger button--ui button--nolink'>Force Push</button> is a destructive action, but this is expected because we have rewritten our branch's history by squashing commits.
