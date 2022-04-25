---

title: Other Integrations
description: Learn how to authenticate with GitKraken Client to manage your SSH keys for repositories and integrations.  Create a SSH key pair or bring your own!
taxonomy:
    category: gitkraken-client

---

GitKraken Client can connect to repositories hosted on most services (like TFS, AWS CodeCommit, [Google Cloud Source Repositories](/integrations/authentication/#google-cloud-source-repositories), custom service, etc), over HTTPS or SSH.


***
## HTTPS
The most common and default way to interact with a remote repository, HTTPS configuration will always require your Git username and password credentials.

To clone a remote repository over HTTPS, first navigate to your hosting service and copy the HTTPS link. The URL should be formatted like this:


    https://example.com/username/myrepository.git



Then go to GitKraken Client and clone the project through <em class='context-menu'>File <i class="fa fa-caret-right"></i> Clone</em>.

<img src='/img/documentation/getting-started/clone.png' srcset='/img/documentation/getting-started/clone@2x.png 2x' class='img-bordered img-responsive center'>

Paste the URL, hit <button class='button button--success button--ui button--nolink'>Clone the repo</button>, and then open the repo in GitKraken. 

By default when cloning a repo using HTTPS, your remote tracking at `origin` will be set using this format.

***
## SSH

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/z7jVOenqFYk?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

Before you can clone a repo over SSH, you must first set up your SSH keys in GitKraken Client.

Navigate to <em class='context-menu'>Preferences <i class="fa fa-caret-right"></i> SSH</em>.

<img src="/img/documentation/integrations/authentication.png" srcset="/img/documentation/integrations/authentication@2x.png" class="img-bordered img-responsive center">

Here you may choose an SSH key pair by browsing your file system, or let GitKraken Client generate a key for you (recommended). Make sure that you copy your public SSH key and paste it into your remote hosting service!

Once your keys are set up, you are ready to clone.

### Clone over SSH

To clone a remote repository over SSH, first navigate to your hosting service and copy the SSH link.

Then go to GitKraken Client and clone the project through <em class='context-menu'>File <i class="fa fa-caret-right"></i> Clone</em>.

<img src='/img/documentation/getting-started/clone.png' srcset='/img/documentation/getting-started/clone@2x.png 2x' class='img-bordered img-responsive center'>

Paste the URL, hit <button class='button button--success button--ui button--nolink'>Clone the repo</button>, and then open the repo in GitKraken. 

### Supported SSH formats 

The standard protocol can be entered as a remote in one of following formats:

    ssh://{user}@{host}/{repo}

or

    {user}@{host}:{repo}

where

* `{host}` can be example.com
* `{user}` is the username (**git** by default)
* `{repo}` is myrepository.git

<div class='callout callout--basic'>
    <p><strong>Note:</strong><code>{repo}</code> usually has an owner like a user or organization where the repository is located on which <code>ssh://{user}@{host}/{owner}/{repo}</code> would be used.</p>
</div>

For example, the original HTTPS URL in SSH is formulated as

    git@example.com:org/username/myrepository.git

By default when cloning a repo using SSH, your remote tracking at `origin` will be set using this format.


### Custom SSH ports

To use a custom SSH port, you need to use the `ssh://` format for your SSH URL.

    ssh://{user}@{host}:{port}/{repo}



### Local SSH Agent
> "Never send a human to do a machine's job."

A local SSH agent handles key communication with your remote host, without needing a passphrase.

With SSH, it's not uncommon when working with many projects, and separate [profiles](/start-here/profiles) that you need different credentials.

While you can specify a single SSH key pair as a default, and even have dedicated defaults per [profile](/start-here/profiles), it may be preferable to check _Use local SSH agent_ and have the keys managed externally.

This way, provided your keys are loaded, every action requiring a chat with your known hosts can manage providing `l33tp@$$..&3` for success without your keyboard involved.  

100% of the time, it works every time.

### I'm having an SSH issue.
Well if it's not working 100% of the time, the most common issues are:

* SSH-agent on Windows &mdash; GitKraken Client currently only supports Pageant for the SSH agent for Windows.
 * You can download PuTTY and Pageant from their page <a href='http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html' target='_blank'>here</a>.
* Misconfigured SSH settings &mdash; remote URL format
 * Check in <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> Authentication</em> to confirm that your SSH settings are correct.
 * Edit remotes in the left ref panel to ensure push and pull urls are set and in the correct format
* Expected use of SSH config &mdash; GitKraken Client does not currently respect your SSH config and cannot make use of any remote server nicknames or identities.
 * You can either load your SSH key directly into GitKraken Client or use your system&rsquo;s SSH agent to authenticate with your remote.


***
## Forget all

You may tell GitKraken to forget all usernames and passwords from <em class='context-menu'> Preferences <i class='fa fa-caret-right'></i> Authentication</em>:

<img src="/img/documentation/integrations/forget-all.png" srcset="/img/documentation/integrations/forget-all@2x.png" class="img-bordered img-responsive center">

Use this if you need the app to prompt for username or password for remote actions like push or pull.

***

## Proxy configuration

GitKraken Client supports proxies for Windows, OSX, and Linux. GitKraken Client should recognize your proxy settings by default, however please review the additional instructions below if you are using an authenticated proxy such as <em>basic</em>, <em>NTLM</em>, <em>Negotiate</em>, or <em>Digest</em>.

### Windows

For Windows users, your Windows machine will prompt for your proxy credentials on GitKraken’s behalf. Enter the credentials to complete the proxy configuration with GitKraken Client.

### OSX

If you’re using an authenticated proxy on OSX, GitKraken will directly ask for the proxy credentials. Enter the credentials to complete the proxy configuration with GitKraken Client.

### Linux
If you are using an authenticated proxy on Linux, GitKraken Client will directly ask for the proxy credentials. Additionally, you will need to run GitKraken Client with the command line flag:

    --proxy-server=10.200.0.1:8080


where <code>10.200.0.1</code> and <code>8080</code> are the proxy IP and proxy port respectively. Without this flag, OAuth integrations are subject to fail.

## Google Cloud Source Repositories

Due to the non-standard way Google Source Cloud Repositories use HTTPS and SSH URLs, GitKraken Client will have trouble parsing the URLs. The SSH URL is normally formatted in this manner:

    ssh://example@gitkraken.com@source.developers.google.com:2021/p/test-project-12345/r/Test-Repo-1

Instead, try replacing the first `@` symbol with `%40`:

    ssh://example%40gitkraken.com@source.developers.google.com:2021/p/test-project-12345/r/Test-Repo-1
