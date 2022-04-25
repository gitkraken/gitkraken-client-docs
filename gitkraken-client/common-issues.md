---

title: Common Issues
description: Learn about common issues that you may encounter when using GitKraken Client.
taxonomy:
    category: gitkraken-client

---

***
## Integration - 1000 Error (1002, 1003, 1005, 1007)
When attempting to connect to one of our integrations, you may see `Error 1002`, `Error 1003`, `Error 1005` or `Error 1007`.

<img src="/img/documentation/known-issues/error-1002.png" srcset="/img/documentation/known-issues/error-1002@2x.png 2x" class="img-responsive center img-bordered">

### Solution:
These are general authentication errors.  First, verify you used the correct credentials then try one of the following potential solutions:

- If your credentials are correct, you can try signing out of the service in your default browser first, and then attempting the authentication from GitKraken Client again.

- Clear your browser cache, sign out of the git hosting service, then restart GitKraken Client and try again.

- If that is not working you can also try changing your operating system default browser to be a different browser. Once this is changed you can restart GitKraken Client and attempt to authenticate again.

If that still does not work, please contact our [support team](https://www.gitkraken.com/contact) and we can troubleshoot further.

 
***

## Error when pushing a branch
When attempting to push a branch, you may see the following `Push Failed: Cannot read property 'fullName' of undefined` error:

<img src="/img/documentation/known-issues/push-error.png" class="img-responsive center img-bordered">

### Solution:
This usually indicates that there is a casing difference between the local branch and the upstream remote branch.  You can rename the local branch to match the casing of the upstream remote branch, which will allow you to push the changes.  

<div class='callout callout--warning'>
    <p>Note: You may need an intermediate name change to get the branch named correctly.  For example: Test-branch > temp-name > test-branch</p>
</div>

## Some branches or files not appearing - Capitalization issue

This most often occurs when having multiple remote banches nested together, but the capitalization differs. For example: Feature/foo and feature/foo may either be detected as the same branch OR a different branch depending on how your Operating Sytem treats capitalization.

This can cause some branches to not appear in GitKraken. This can also apply to naming files with same name and different capitalization.

 To avoid these capitalization issues, we reccomend giving each branch and remote a unique name.

## Cannot log in - Cannot read property 'email' of null
When trying to log in, you may see the following error: `Cannot read property 'email' of null`. This is commonly related to a network issue such as a proxy, firewall, or security application. The most common occurrence is something like Zscaler.

### Solution:
If you have any of the above in place try the following:

- Sign in with GitHub authentication
- Approve the GitKraken application
- Continue as free with 0 days
- Click on free icon in bottom right, this brings up a web page inside GitKraken Client which authenticates against Zscaler
- Restart GitKraken Client and authenticate normally

This should allow you to log in without issue. If that still does not work, please contact our [support team](https://www.gitkraken.com/contact) and we can troubleshoot further.

Error not here? Check out our [technical issues FAQ](/faq/#technical-issues)

## Windows taskbar icon is not showing the GitKraken logo
Some Windows users are seeing the taskbar icon show incorrectly for GitKraken. This is due to the start menu shortcut moving from `C:\Users\USER\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Axosoft, LLC` to `C:\Users\USER\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\GitKraken`. 

### Solution:
You can delete the old folder `C:\Users\USER\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Axosoft, LLC`, start GitKraken from the start menu, and then pin it to the taskbar again to resolve this.
