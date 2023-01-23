---

title: Common Issues
description: Learn about common issues that you may encounter when using GitKraken Client.
taxonomy:
    category: gitkraken-client

---

***
## Integration - 1000 Error (1002, 1003, 1005, 1007)
When attempting to connect to one of our integrations, you may see `Error 1002`, `Error 1003`, `Error 1005` or `Error 1007`.

<img src="/wp-content/uploads/error-1002.png" srcset="/wp-content/uploads/error-1002@2x.png 2x" class="img-responsive center img-bordered">

### Solution:
These are general authentication errors.  First, verify you used the correct credentials then try one of the following potential solutions:

- If your credentials are correct, you can try signing out of the service in your default browser first, and then attempting the authentication from GitKraken Client again.

- Clear your browser cache, sign out of the git hosting service, then restart GitKraken Client and try again.

- If that is not working you can also try changing your operating system default browser to be a different browser. Once this is changed you can restart GitKraken Client and attempt to authenticate again.

If that still does not work, please contact our [support team](https://www.gitkraken.com/contact) and we can troubleshoot further.

 
***

## Error when pushing a branch
When attempting to push a branch, you may see the following `Push Failed: Cannot read property 'fullName' of undefined` error:

<img src="/wp-content/uploads/push-error.png" class="img-responsive center img-bordered">

### Solution:
This usually indicates that there is a casing difference between the local branch and the upstream remote branch.  You can rename the local branch to match the casing of the upstream remote branch, which will allow you to push the changes.  

<div class='callout callout--warning'>
    <p>Note: You may need an intermediate name change to get the branch named correctly.  For example: Test-branch > temp-name > test-branch</p>
</div>

***

## Some branches or files not appearing - Capitalization issue

This most often occurs when having multiple remote banches nested together, but the capitalization differs. For example: `Feature/foo` and `feature/foo` may either be detected as the same branch OR a different branch depending on how your operating sytem treats capitalization. Most often this appears on Windows machines.

Symptoms:

- Branches not appearing in GitKraken - only one of the branches will be detected when they share a name. 
- This can also apply to files. If two files share the same name with only different capitalization one may appear deleted, moved, or not at all.
- This can also manifest as the file being staged but not showing as staged when running a `git status`.

To avoid these capitalization issues, we recommend giving each branch, file, and remote a unique name.

***

## Cannot log in - Cannot read property 'email' of null
When trying to log in, you may see the following error: `Cannot read property 'email' of null`. This is commonly related to a network issue such as a proxy, firewall, or security application. The most common occurrence is something like Zscaler.

### Solution:
If you have any of the above in place try the following:

- Sign in with GitHub authentication
- Approve the GitKraken application
- Continue as free with 0 days
- Click on free icon in bottom right, this brings up a web page inside GitKraken Client which authenticates against Zscaler
- Restart GitKraken Client and authenticate normally

This should allow you to log in without issue.

***

## Windows taskbar icon is not showing the GitKraken logo
Some Windows users are seeing the taskbar icon show incorrectly for GitKraken. This is due to the start menu shortcut moving from ``C:\\Users\\USER\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Axosoft, LLC`` to ``C:\\Users\\USER\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\GitKraken``. 

### Solution:
You can delete the old folder ``C:\\Users\\USER\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Axosoft, LLC``, start GitKraken from the start menu, and then pin it to the taskbar again to resolve this.

## Why can't I see my GitHub remotes or repositories in the drop down menu? Why am I getting an error about GitHub organization permissions?

In order to work with with a repository owned by a GitHub organization with the GitHub integrtion connected, you need an organization to first allow access.

<img src="/wp-content/uploads/error.png" class="img-bordered img-responsive center">

* First check to see if access is allowed to GitKraken from your profile's [GitHub Applications](https://github.com/settings/connections/applications/a7557949433b7d282a76)
* If access has been allowed, then the organization will need to allow [Organization Approval](https://help.github.com/articles/requesting-organization-approval-for-your-authorized-applications/)
* If you are attempting to use GitKraken with a repository owned by a different individual, consider forking their repository to use GitKraken for your changes. Otherwise this other individual will need to first [install GitKraken](/gitkraken-client/how-to-install/) and connect it to GitHub to authorize GitKraken.
* For details about third-party application restrictions view [Third-party apps list](https://help.github.com/articles/about-third-party-application-restrictions/)
