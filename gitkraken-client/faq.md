---

title: GitKraken Desktop FAQ
description: Frequently Asked Questions about GitKraken Desktop
taxonomy:
    category: gitkraken-client

---

The answers to your important **F**requently **A**sked **Q**uestions.

<div class='faq container'>
    <section class='pts pbm'>
        <div class='callout'>
            <h4>Just a sec! Before you dive in, perhaps one of these resources might help?</h4>
            <ul class='dl-list plm prm'>
                <li>📝 <a href='https://www.gitkraken.com/resources/gitkraken-cheat-sheet' target="_blank" rel='noopener'><em>GitKraken Desktop</em> Cheat Sheet</a></li>
                <li>📝 <a href='https://www.gitkraken.com/resources/gitkraken-github-cheat-sheet' target="_blank" rel='noopener'><em>GitKraken Desktop for GitHub Users</em> Cheat Sheet</a></li>
            </ul>
        </div>
    </section>
</div>
        
        
        
## Features & interface

***

### Does GitKraken Desktop support Visual Studio Team Service, TFS, or Azure DevOps?
Yes, for Azure DevOps (previously VSTS), you can use our integration with [Azure DevOps](/integrations/azure-devops/)!

For TFS instances you will need to clone your repo <kbd><strong>File > Clone Repo</strong></kbd> and then enter the HTTPS repository URL (which can be found at the top-right of your Code page).<br><br>
Enable _Basic Authentication_ in IIS for TFS if you're connecting to a remote TFS Git server from a Mac or Linux.

If authenticating to TFS via username and password is not working, try creating a Personal Access Token (PAT) to use in place of a password.

Check out our [SSH and HTTPS](/integrations/authentication) page for more information.

***

### What Linux distributions are supported by GitKraken Desktop?
GitKraken Desktop currently supports Ubuntu 16.04 LTS+, RHEL 7+, CentOS 7+, and Fedora 30+. While GitKraken Desktop might be able to be installed on other distros, we cannot guarantee that it will behave properly.

***

### How can I use multiple GitHub / GitLab / Bitbucket / Azure DevOps accounts with GitKraken?
By default, GitKraken Desktop connects to one integration at a time. However, a <a href='https://gitkraken.com/features'>paid GitKraken license</a> provides multiple profile support, allowing you to easily switch between profiles that each have their own associated integrations.

If you have a GitKraken Pro, Teams, or Enterprise license, [set up profiles](/start-here/profiles) to configure a GitHub, GitLab, Bitbucket, or Azure DevOps account for each profile.

***

### How do I change the avatar associated with my commits?
Your commit avatar in your GitKraken Desktop is linked to the <a href='https://gravatar.com/' target='_blank'>Gravatar</a>, which is linked to your <code>.gitconfig</code> email address. If you change your Gravatar, your avatar in your GitKraken Desktop will update itself.

***

### Can I use my GitKraken paid license on more than one computer?
Yes, your GitKraken paid subscription is associated with your email address, not a specific computer. So you can use GitKraken Desktop on as many computers as you'd like. 🖥️

***

### Why can't I see remotes under my integration drop-down menu?
The remote drop-down menu is for adding remotes from an integration (such as GitHub, GitLab, Bitbucket, etc.) and will only display **forks** of the repository. To add a remote that is not a fork, use the URL option instead.

***

### How do I push a local project from my GitKraken Desktop to GitHub, Bitbucket, GitLab, or Azure DevOps?

You need to change your branch's upstream and force push. 

- [Initialize](/working-with-repositories/open-clone-init/#initialize-a-new-project) a blank project on GitHub, GitLab, Bitbucket, or Azure DevOps.
- [Open](/working-with-repositories/open-clone-init/#opening-an-existing-project) your local project in GitKraken.
- Add your newly initialized project as a [remote](/working-with-repositories/pushing-and-pulling/) using the URL option.
- Update your branch's [upstream](/working-with-repositories/pushing-and-pulling/#setting-the-upstream-branch) so it points to your new remote.
- Push the branch. You will be prompted to <button class='button button--danger button--ui button--nolink'>Force Push</button>, which is the correct action to take for this use case.

You are done! Your local project is now on your hosting service. 

***

### How do I sign out of GitKraken?

You may sign into a different account by selecting your profile icon in the top right corner and selecting _Sign into a different account_. 

While there is no way to sign out of GitKraken, you may delete all of your GitKraken data by deleting the `~/.gitkraken` folder. You can find the Data Location for your operating system [here](/gitkraken-client/how-to-install/).

## Technical issues

***
### I receive a "Could not find a compatible repository" for one of my repos. How can I fix that?

That error usually indicates something is stopping GitKraken from opening the repo.  If you have this project open in another tool, such as an IDE,  try closing that application and then relaunching GitKraken Desktop.

If you have git installed, try running `git status` from the terminal. If you have pending changes, try stashing or committing those changes or switching branches, and see if that allows you to load the repo in GitKraken Desktop.  

There could also be an issue with the directory path itself. Try cloning this repository to a different local directory.


***

### I just downloaded GitKraken Desktop and it is not working.
If you are on Linux and are unable to launch GitKraken Desktop after installation, try to launch the application from the terminal to verify that there are no missing dependencies. Also, be sure to check out our page on [How to Install GitKraken Desktop.](/gitkraken-client/how-to-install)

***

### I just subscribed but FREE is still shown in the lower right corner.
Be sure you are logged in with the same email address registered with your GitKraken subscription. Click your profile icon in the upper right corner to check which email you're using or to sign into your account.

<img src="/wp-content/uploads/sign-into-a-different-account.png" class="img-responsive center img-bordered">

***

### I'm having an SSH issue.
The most common issues are:

* Misconfigured SSH settings &mdash; If you are using SSH (your remote URL takes the form of `ssh://{host}/{repo}` or `{user}@{host}:{repo}`), go to <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> Authentication</em> to confirm that your SSH settings are correct.

* Use of SSH config &mdash; GitKraken Desktop does not currently respect your SSH config and cannot make use of any remote server nicknames or identities. You can either load your SSH key directly into GitKraken Desktop or use your system&rsquo;s SSH agent to authenticate with your remote.

* SSH-agent on Windows &mdash; GitKraken Desktop currently only supports Pagent for the SSH agent.  You can download PuTTY and Pagent from their page <a href='http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html' target='_blank'>here</a>.

***

### I can't view any of my GitHub remotes from GitKraken Desktop.
GitKraken needs to be authorized in your GitHub account in order to browse remote repositories, view and create pull requests, and perform other actions. You can double-check that GitKraken is authorized from <a href='https://github.com/settings/applications' target='_blank'>your GitHub authorized applications page</a>.<br><br>
If GitKraken is authorized on your GitHub account, you should be able to browse and connect to any of your personal repositories. However to connect to any repositories owned by an organization, GitKraken usually also needs to be authorized by the organization. After authorizing GitKraken on your own account, you can make access requests to your organizations from <a href='https://github.com/settings/connections/applications/a7557949433b7d282a76' target='_blank'>here</a>. Requests must be approved by organization owners, as explained in <a href='https://help.github.com/articles/approving-third-party-applications-for-your-organization/' target='_blank'>GitHub's documentation</a>.<br><br>
If you are attempting to use GitKraken Desktop with a repository owned by a different individual, consider forking their repository to use GitKraken Desktop for your changes. Otherwise this other individual will need to first <a href='https://gitkraken.com/download' target='_blank'>install GitKraken Desktop</a> and [connect it to GitHub](/integrations/github) to authorize GitKraken.

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

### My commit graph is not showing up correctly.
Sometimes a repository can get in an unexpected state that causes it to not work correctly in GitKraken Desktop. This may be your commit graph not showing up at all or seeing the message "Displaying 2000 commits".

Try running [git gc](https://git-scm.com/docs/git-gc) from the terminal on this repository and then relaunching your GitKraken Desktop. You can also try taking a fresh clone of the repository in a new location.

***

### I'm having display or graphical issues 
Hardware acceleration may cause graphical instability or other issues on some systems, such as GitKraken Desktop displaying in a blank window.

You can disable GPU hardware acceleration by running GitKraken Desktop from a command line with the the following command:
```
gitkraken --disable-gpu
```
***

### My files are not showing up as expected or have strange characters.
GitKraken Desktop expects most files to use `UTF-8` file encoding. If you are using another encoding type, you can set your type at the top when editing your file, or per-repository from the preferences menu.

You can also set your file encoding to `GUESS ENCODING` and GitKraken Desktop will try to match the file encoding so that it is displayed correctly. Take care to select the correct file encoding when editing the file, as selecting the incorrect encoding could lead to unexpected errors.



***

### How to get SILLY (extended) logs

Obtain extended SILLY (extended) logs by doing the following:

* Close GitKraken
* (optional) Rename or move the \logs folder under ~\.gitkraken\logs. The data location for this folder on your OS can be found [here](/gitkraken-client/how-to-install/)
* Start GitKraken from the CLI using the command `gitkraken -d SILLY`
* All logs will be under the \logs folder
* Reproduce the issue or error

***

<br>
Can't find your question here? <a href='https://help.gitkraken.com/gitkraken-client/contact-support/'>Contact us</a> and ask away.
