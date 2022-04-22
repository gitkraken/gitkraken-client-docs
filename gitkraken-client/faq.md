---

title: Frequently Asked Questions about GitKraken Client
description:
taxonomy:
    category: gitkraken-client

---

The answers to your important **F**requently **A**sked **Q**uestions.

<div class='faq container'>
    <section class='pts pbm'>
        <div class='callout'>
            <h4>Just a sec! Before you dive in, perhaps one of these resources might help?</h4>
            <ul class='dl-list plm prm'>
                <li><i class="far fa-file-pdf"></i> <a href='https://www.gitkraken.com/resources/gitkraken-cheat-sheet' target="_blank" rel='noopener'><em>GitKraken Client</em> Cheat Sheet</a></li>
                <li><i class="far fa-file-pdf"></i> <a href='https://www.gitkraken.com/resources/gitkraken-github-cheat-sheet' target="_blank" rel='noopener'><em>GitKraken Client for GitHub Users</em> Cheat Sheet</a></li>
            </ul>
        </div>
    </section>
</div>
        
        
        
## Features & interface

***

### Does GitKraken Client support TFS, Visual Studio Team Service or Azure DevOps?
Yes, for Azure DevOps (previously VSTS), you can use our integration with [Azure DevOps](/integrations/visual-studio-team-services/)!

For TFS instances you will need to clone your repo <em class='context-menu'>File <i class='fa fa-caret-right'></i> Clone Repo</em> and then enter the HTTPS repository URL (which can be found at the top-right of your Code page).<br><br>
If you're connecting to a remote TFS Git server from a Mac or Linux, you will need to enable _Basic Authentication_ in IIS for TFS.

If authenticating to TFS via username and password is not working, try creating a Personal Access Token (PAT) to use in place of a password.

For more information authenticating with repos, check out our [SSH and HTTPS](/integrations/authentication) page.

### What Linux distributions are supported by GitKraken Client?
GitKraken Client currently supports Ubuntu 16.04 LTS+, RHEL 7+, CentOS 7+, and Fedora 30+. While GitKraken Client might be able to be installed on other distros, we cannot guarantee that it will behave properly.

***

### How can I see what commands GitKraken Client makes to the CLI?
Unlike other Git GUI clients, GitKraken Client is not a front-end GUI for your command line. It works directly with your repositories with no dependencies, which means a separate Git installation isn&rsquo;t required. 

***

### How can I use multiple GitHub / GitLab / Bitbucket / Azure DevOps accounts with GitKraken?
By default, GitKraken Client connects to one integration at a time. However, with <a href='https://gitkraken.com/features'>GitKraken Pro</a>&lsquo;s multiple profile support, you can easily switch between profiles that each have their own associated GitHub and BitBucket accounts.<br><br>
If you have PRO, [set up profiles](/start-here/profiles) to configure a GitHub, GitLab, Bitbucket, or Azure DevOps account for each profile.

***

### How do I change the avatar associated with my commits?
Your commit avatar in your GitKraken Client is linked to the <a href='https://gravatar.com/' target='_blank'>Gravatar</a>, which is linked to your <code>.gitconfig</code> email address. If you change your Gravatar, your avatar in your GitKraken client will update itself.

***

### Can I use my GitKraken paid license on more than one computer?
Yes, your GitKraken paid subscription is associated with your email address, not a specific computer. So you can use GitKraken Client on as many computers as you'd like. 🖥️

***

### Why can't I see remotes under my integration drop-down menu?
The remote drop-down menu is for adding remotes from an integration (such as GitHub, GitLab, Bitbucket, etc.) and will only display **forks** of the repository. To add a remote that is not a fork, use the URL option instead.

***

### How do I push a local project from my GitKraken Client to GitHub, Bitbucket, GitLab, or Azure DevOps?

You need to change your branch's upstream and force push. 

- [Initialize](/working-with-repositories/open-clone-init/#initialize-a-new-project) a blank project on GitHub, GitLab, Bitbucket, or Azure DevOps.
- [Open](/working-with-repositories/open-clone-init/#opening-an-existing-project) your local project in GitKraken.
- Add your newly initialized project as a [remote](/working-with-repositories/pushing-and-pulling/) using the URL option.
- Update your branch's [upstream](/working-with-repositories/pushing-and-pulling/#setting-the-upstream-branch) so it points to your new remote.
- Push the branch. You will be prompted to <button class='button button--danger button--ui button--nolink'>Force Push</button>, which is the correct action to take for this use case.

You are done! Your local project is now on your hosting service. 

***

### Can I access repos for GitHub Enterprise, GitLab Self-Managed, Bitbucket Server or Azure DevOps with my Individual subscription?

Yes you can! From a new tab navigate to<em class='context-menu'>Clone a repo <i class='fa fa-caret-right'></i> Clone <i class='fa fa-caret-right'></i>Clone with URL</em>. From here enter the remote [SSH or HTTPS](https://support.gitkraken.com/integrations/authentication/#https) URL and click <button class='button button--success button--ui button--nolink'>Clone the repo!</button>. 

***

### How do I sign out of GitKraken?

You may sign into a different account by selecting your profile icon in the top right corner and selecting _Sign into a different account_. 

While there is no way to sign out of GitKraken, you may delete all of your GitKraken data by deleting the `~./gitkraken` folder. You can find the Data Location for your operating system [here](/how-to-install/).

## Technical issues

***
### I receive a "Could not find a compatible repository" for one of my repos. How can I fix that?

That error usually indicates something is stopping GitKraken from opening the repo.  If you have this project open in another tool, such as an IDE,  try closing that application and then relaunching GitKraken Client.

If you have CLI installed, try running `git status`. If you have pending changes, try stashing or committing those changes or switching branches, and see if that allows you to load the repo in GitKraken Client.  

On Windows machines, it is possible that a file path became [too long](https://support.gitkraken.com/start-here/preferences/#longpaths-windows-only).

There could also be an issue with the directory path itself. Try cloning this repository to a different local directory.


***

### I just downloaded GitKraken Client and it is not working.
If you are on Linux and are unable to launch GitKraken Client after installation, try to launch the application from the terminal to verify that there are no missing dependencies. Also, be sure to check out our page on [How to Install GitKraken Client.](/how-to-install)

***

### I just subscribed but I do not see PRO in the lower right corner.
Be sure you are logged in with the same email address registered with your GitKraken Pro subscription. Click your profile icon in the upper right corner to check which email you're using or to sign into your account.

<img src="/img/documentation/managing-organizations/login/sign-into-a-different-account.png" srcset="/img/documentation/managing-organizations/login/sign-into-a-different-account@2x.png 2x" class="img-responsive center img-bordered">

***

### I'm having an SSH issue.
The most common issues are:

* Misconfigured SSH settings &mdash; If you are using SSH (your remote URL takes the form of <code>ssh://{host}/{repo}</code> or <code>{user}@{host}:{repo}</code>), go to <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> Authentication</em> to confirm that your SSH settings are correct.

* Use of SSH config &mdash; GitKraken Client does not currently respect your SSH config and cannot make use of any remote server nicknames or identities. You can either load your SSH key directly into GitKraken Client or use your system&rsquo;s SSH agent to authenticate with your remote.

* SSH-agent on Windows &mdash; GitKraken Client currently only supports Pagent for the SSH agent.  You can download PuTTY and Pagent from their page <a href='http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html' target='_blank'>here</a>.

***

### I can't view any of my GitHub remotes from GitKraken Client.
GitKraken needs to be authorized in your GitHub account in order to browse remote repositories, view and create pull requests, and perform other actions. You can double-check that GitKraken is authorized from <a href='https://github.com/settings/applications' target='_blank'>your GitHub authorized applications page</a>.<br><br>
If GitKraken is authorized on your GitHub account, you should be able to browse and connect to any of your personal repositories. However to connect to any repositories owned by an organization, GitKraken usually also needs to be authorized by the organization. After authorizing GitKraken on your own account, you can make access requests to your organizations from <a href='https://github.com/settings/connections/applications/a7557949433b7d282a76' target='_blank'>here</a>. Requests must be approved by organization owners, as explained in <a href='https://help.github.com/articles/approving-third-party-applications-for-your-organization/' target='_blank'>GitHub's documentation</a>.<br><br>
If you are attempting to use GitKraken Client with a repository owned by a different individual, consider forking their repository to use GitKraken Client for your changes. Otherwise this other individual will need to first <a href='https://gitkraken.com' target='_blank'>install GitKraken Client</a> and [connect it to GitHub](/integrations/github) to authorize GitKraken.

***

### I'm having an issue using GitKraken behind a firewall.
GitKraken should activate and run automatically behind standard firewall setups. Due to the highly variable nature of firewall configurations, we cannot troubleshoot individually, nor can we guarantee that your setup will be compatible with GitKraken.

***

### I can't get GitKraken to run behind a proxy. Is there anything I can do to make it work?
GitKraken supports both authenticated and non-authenticated proxies, but some PACs and URL-based settings still may not work. If this applies to you, there are some workarounds (please note that there is no guarantee that these fixes will work for all users):

* If you're having issues using GitKraken through a proxy, use the <a href="https://git-scm.com/docs/git-config#git-config-httpproxy" target="_blank"><code>http.proxy</code></a> Git config setting. Add your proxy to this file and give it a whirl.

* If that doesn't work, configuring <a href="https://git-scm.com/docs/git-config#git-config-remoteltnamegtproxy" target="_blank"><code>remote.&lt;name&gt;.proxy</code></a> might help. Bear in mind that local (repo-specific) settings override the settings your global Git config.

Learn more on our [SSH, HTTPS, & Proxies](/integrations/authentication) page.

***

### GitKraken Client keeps spinning when opening a repo. Can I use it with repos on DropBox or OneDrive?
GitKraken does not support opening repos hosted on DropBox or OneDrive. We recommend moving your repo to a location on your machine, and then opening the repo from there.

***

### My commit graph is not showing up correctly.
Sometimes a repository can get in an unexpected state that causes it to not work correctly in GitKraken Client. This may be your commit graph not showing up at all or seeing the message "Displaying 2000 commits".

Try running [git gc](https://git-scm.com/docs/git-gc) from the terminal on this repository and then relaunching your GitKraken Client. You can also try taking a fresh clone of the repository in a new location.

***

### My files are not showing up as expected or are marked as binary.
GitKraken Client only supports `UTF-8` file encoding. Files may display in an unexpected way or be marked a binary if files are not encoded in UTF-8. 

You can use and [external diff and merge tools](/working-with-repositories/branching-and-merging/#external-merge-tools) to work on files using other encoding types.

***

<br>
Can't find your question here? <a href='https://www.gitkraken.com/contact'>Contact us</a> and ask away.