---

title: Open, Clone, and Init
description: Learn the basics of GitKraken Client, like initializing or cloning projects!
taxonomy:
    category: gitkraken-client

---

Whether you are a newborn or a wizened deep-ocean octopod, each user will need to open, clone, or initialize a repo in GitKraken Client.

<div class='embed-container embed-container--16-9'>
    <iframe width='560' height='315' src='https://www.youtube.com/embed/8uxrA56VJgY?rel=0&vq=hd1080' frameborder='0' allowfullscreen></iframe>
</div>

***
## Setup
The essential setup process includes:

1. [Installing](/gitkraken-client/how-to-install) GitKraken Client
2. Creating an account and setting up your [profile](/gitkraken-client/profiles)

Once this is complete, you are ready for your oceanic journey!

***
## Projects in GitKraken Client
There are three ways to start a Git repository when working on a project:

1. **Open** - Open a local Git repository already initialized and available locally.
2. **Clone** - Clone a remote Git repository already initialized.
3. **Init** - Create an empty Git repository or reinitialize an existing one.

***

### Opening an existing project
GitKraken Client allows you to load your existing repositories and pick up where you left off. It's also useful for visualizing past work done.  

If you're coming from a Git project you already have locally, navigate to <kbd><strong>File > Open Repo</strong></kbd> to get started immediately in GitKraken Client.

<img src='/wp-content/uploads/project.png' srcset='/wp-content/uploads/project@2x.png 2x' class='img-bordered img-responsive center'>

***
### Cloning an existing project

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/OA9o09Bq5M8?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

If your project is not on your local machine or you want a new copy, clone the project through <kbd><strong>File > Clone</strong></kbd>.

<img src='/wp-content/uploads/clone-url.png' srcset='/wp-content/uploads/clone-url@2x.png 2x' class='img-bordered img-responsive center'>

This will then prompt you to open the newly copied project in GitKraken Client.

***
### Initialize a new project
Starting a project in GitKraken Client is easy through <kbd><strong>File > Init</strong></kbd>

<img src='/wp-content/uploads/init.png' srcset='/wp-content/uploads/init@2x.png 2x' class='img-bordered img-responsive center'>

All you need to do is fill out the fields and select <button class='button button--success button--ui button--nolink'>Create Repository</span></button> for the magic to begin.

#### Input
* New repository path
* `.gitignore` template (**optional**)
 * Automatically creates a `.gitignore` file in your working copy.

* License (**optional**)
 * On init, GitKraken Client will create a `LICENSE` file in your repository.
 * Check out the [Open Source Initiative](https://opensource.org/licenses) or find out more about [Choosing a License](http://choosealicense.com/).

#### Output
* A new initialized Git project at the specified repository path by creating a `.git` folder.
* The project is opened in GitKraken Client
* An "Initial commit" on a `master` branch containing a blank `README.md` along with a `.gitignore` and `LICENSE.md` if applicable.

 <div class='callout callout--success'>
     <p>GitKraken Client also allows initializing a repository directly to a remote Git hosting provider such as GitHub and Bitbucket.</p>
 </div>


***

### Delete a repository

You may delete a repository by first navigating to the folder icon in the upper left corner of GitKraken Client UI.

<img src='/wp-content/uploads/click-folder.png' srcset='/wp-content/uploads/click-folder@2x.png 2x' class='img-bordered img-responsive center'>

Then browse through your repo list and right-click on the repository you wish to delete from your local machine. 

<img src='/wp-content/uploads/delete-repo.png' srcset='/wp-content/uploads/delete-repo@2x.png 2x' class='img-bordered img-responsive center'>

If you are unable to delete the repository, first make sure it is closed in GitKraken Client and then close any other applications which may be working with files in the repository. Restart GitKraken Client and try the delete again.

Deleting the repo from within GitKraken Client will only delete your local copy of the repository. If you wish to delete your remote repository, you will need to perform that action directly by logging into your remote hosting service (GitHub, GitLab, etc).
