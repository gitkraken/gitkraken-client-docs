---

title: Performance Issues
description: What to do if GitKraken Client is performing poorly
taxonomy:
    category: gitkraken-client

---

We're always on a quest to streamline the git experience as well as improve the performance of GitKraken Client. If you're experiencing slow performance, it can often be remedied using one of the troubleshooting steps below.

***

### Improving Performance

Perfomance issues in GitKraken Client are often related to a specific repository. Some large or complex repositories with many references may cause GitKraken Client to slow down. 

#### How to troubleshoot slow performance

- Perform a [git gc](https://git-scm.com/docs/git-gc) on the repository.  

- Take a fresh clone of the repository to a new local directory.

#### Additional troubleshooting steps

- Disable auto-fetch by setting the [Auto-fetch](/gitkraken-client/preferences/#auto-fetch) Interval to 0. 

- Perform a [git status](https://git-scm.com/docs/git-status) on the repository.

- [Delete local branches](branching-and-merging/#delete-a-branch) that are not needed. 

- [Soloing or Hiding](/gitkraken-client/hiding-and-soloing/) branches/tags.

- Set the Max Commits in Graph to [show fewer commits](/gitkraken-client/preferences/#max-commits-in-graph).

- If [working with an LFS repository](/gitkraken-client/git-lfs/), you can perfom an LFS prune.

- Restart GitKraken Client daily
