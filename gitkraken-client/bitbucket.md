---

title: GitKraken Client Bitbucket Integration
description: Integrate GitKraken with your Bitbucket repository by following these steps.
taxonomy:
    category: gitkraken-client

---

GitKraken Client allows you to authenticate with Bitbucket, which will help you find repos on Bitbucket when cloning or adding your remotes.

**Benefits**

* Create repositories on Bitbucket account including .gitignore and license
* Easily generate an SSH key pair and copy to clipboard to add to Bitbucket
* Save authentication into profiles
* Clone from Bitbucket repo list
* Add remotes for Bitbucket repos
* Create and view Pull Requests

<div class='embed-container embed-container--16-9'>
    <iframe width='560' height='315' src='https://www.youtube.com/embed/sQ4ouJpAeR8?rel=0&vq=hd1080' frameborder='0' allowfullscreen></iframe>
</div>

***

## Connecting to Bitbucket

To authenticate with Bitbucket, navigate to the upper right corner to access <kbd><i> <i class="fas fa-cog"></i> Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>

<img src="/wp-content/uploads/preferences.png" srcset="/wp-content/uploads/preferences@2x.png" class="img-bordered img-responsive center">

Or alternatively if you are in the <kbd>New Tab</kbd> view, click on <kbd>Preferences</kbd> under <strong>Customize</strong>.

<img src="/wp-content/uploads/customize.png" srcset="/wp-content/uploads/customize@2x.png" class="img-bordered img-responsive center">

From the Integrations window, select Bitbucket.org and then hit the <button class='button button--success button--ui button--nolink'>Connect to Bitbucket</span></button> button.

<img src="/wp-content/uploads//preferences-authentication.png" srcset="/wp-content/uploads//preferences-authentication@2x.png 2x" class="img-responsive center img-bordered">

This will open a web browser where you will need to log in with your Bitbucket credentials to allow GitKraken access.

Upon login, you'll see a success message below and the connection will be active in GitKraken Client.

<img src="/wp-content/uploads//bitbucket-success.png" srcset="/wp-content/uploads//bitbucket-success@2x.png 2x" class="img-responsive center img-bordered">

***
## Generating SSH keys for Bitbucket.
<div class='callout callout'>
    <p>Note 📝 - GitKraken Client uses your SSH key defined in <kbd><i>Preferences  <i class='fa fa-caret-right'></i>  SSH</i></kbd> for git operations unless you set up a BitBucket-specific SSH key, or enable your local SSH Agent.</p>
</div>

Once your Bitbucket account has been connected to GitKraken, you may then generate an SSH key and add it to your Bitbucket account from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>    Integrations</i></kbd>

Click <button class='button button--success button--ui button--nolink'>Generate SSH key and copy to clipboard</span></button> and add the key to your [Bitbucket](https://bitbucket.org) account settings.

<img src='/wp-content/uploads//generate-ssh.png' srcset='/wp-content/uploads//generate-ssh@2x.png' class='center img-responsive img-bordered'>

***
## OAuth integration with Bitbucket
GitKraken's integration with Bitbucket provides handy information about your repositories.

First, you may search through your existing repositories when cloning:

<img src="/wp-content/uploads//clone.png" srcset="/wp-content/uploads//clone@2x.png" class="img-bordered img-responsive center">

Next, GitKraken Client presents a list of forks of the current repository when adding remotes:

<img src="/wp-content/uploads//remote.png" srcset="/wp-content/uploads//remote@2x.png" class="img-bordered img-responsive center">

Of course, you still have the option of manually entering repo URLs.

***

## Connecting to multiple Bitbucket accounts

GitKraken connects to one Bitbucket account at a time. However, with GitKraken Pro's multiple <a href="/start-here/profiles">profile</a> support, you can easily switch between profiles that each have their own associated Bitbucket accounts.

***
