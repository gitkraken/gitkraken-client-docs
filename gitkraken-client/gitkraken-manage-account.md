---

title: Manage Account
description: GitKraken account admins, this is where you can change your plan, add or remove users, update billing, cancel, and generally manage your account.
taxonomy:
    category: gitkraken-client
    
---

Whether a solo user on a personal license, or an owner managing multiple teams across organizations, learn how to manage your GitKraken account(s), subscription(s), and organization(s).

***
## Sign-up
Sign-up is easy. If you're logging into GitKraken using another account such as [GitHub](/gitkraken-client/github-gitkraken-client/), you're already done! ✅

If you don't have a GitKraken account yet, [register](https://app.gitkraken.com/register) your account today.

***

## Organizations
The <kbd>Organizations</kbd> section shows your organization(s). Click on an organization to manage the [Users](/gitkraken-client/gitkraken-mange-account/#manage-users/), [Teams](/gitkraken-client/teams/), and Subscriptions.

To access your account and manage your organization(s), navigate to [https://app.gitkraken.com](https://app.gitkraken.com), or click <kbd>Manage Account</kbd> from the user menu dropdown <em class="context-menu"><i class="fa fa-bars"> </i>  </em> in GitKraken.

Once you log into your account, click <kbd><strong>Organization > [Your organization name]</strong></kbd> to add users.

<img src="/wp-content/uploads/subscriptions.png" srcset="/wp-content/uploads/subscriptions@2x.png 2x" class="img-responsive center img-bordered">

### Subscriptions
Subsriptions can be added to an organization by clicking the <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>New Organization</span></button> tab.

<img src="/wp-content/uploads/gk-plans1.png"  class="img-responsive center img-bordered">

Once a subscription is added to the organization owner or admin roles may add users to the account using their email address (see [Manage Users](/gitkraken-client/gitkraken-mange-account/#manage-users/) section below).

### Rename organization

To rename your Organization, log into [https://app.gitkraken.com](https://app.gitkraken.com) as the `Owner` or `Admin` and then navigate to <kbd><strong>Organization > [Your organization name] > Settings</strong></kbd>. 

<img src="/wp-content/uploads/rename.png" class="img-responsive center img-bordered">


Type a new name for the Organization and save.

### Hide organizations

If you have any expired GitKraken subscriptions, you may hide these expired organizations from the left panel of [https://app.gitkraken.com](https://app.gitkraken.com).

<img src="/wp-content/uploads/hide-expired-organizations.png" class="img-responsive center img-bordered">

You can also manually choose to hide an organization in the sidebar from the <kbd><strong>Organization > [Your organization name] > Subscription</strong></kbd> menu.

<img src="/wp-content/uploads/hide-organization.png" class="img-responsive center img-bordered">

Click the <kbd>Show Hidden Organizations</kbd> button to show hidden organizations.


***

## Roles

There are four roles for a GitKraken user within an organization's account. Owners, Admins, and Users all consume a license which allows them to use GitKraken Client. The Billing Contact role does not use a license and is intended only for managing the organization.

* **Owner**: Full use of GitKraken Client. Add or edit users plus access to billing. No one but the owner can transfer ownership.
* **Admin**: Full use of GitKraken Client. Add or edit users plus manage billing.
* **User**: Full use of GitKraken Client. General user.
* **Billing Contact (unlicensed)**: Does not consume a license. Add or edit general users plus manage billing.


<table class='table table--bordered table--shortcuts'>
    <thead>
        <tr>
            <th>Permission</th>
            <th>Owner</th>
            <th>Admin</th>
            <th>User</th>
            <th>Billing Contact</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Licensed to use GitKraken</td>
            <th>X</th>
            <th>X</th>
            <th>X</th>
            <th></th>
        </tr>
        <tr>
            <td>Add, edit, and remove users</td>
            <th>X</th>
            <th>X</th>
            <th></th>
            <th>X</th>
        </tr>
        <tr>
            <td>Create and manage teams</td>
            <th>X</th>
            <th>X</th>
            <th></th>
            <th>X</th>
        </tr>
        <tr>
            <td>Manage billing and purchase licenses</td>
            <th>X</th>
            <th>X</th>
            <th></th>
            <th>X</th>
        </tr>
        <tr>
            <td><a href="/gitkraken-client/gitkraken-mange-account/#transfer-ownership">Transfer ownership</a> of the organization</td>
            <th>X</th>
            <th></th>
            <th></th>
            <th></th>
        </tr>
    </tbody>
</table>


***
## Manage users

### Allocating licenses
1. Under <kbd><strong>Organization > [Your organization name]</strong></kbd>, click <button class='button button--success button--ui button--nolink'>Add User</button>
2. Enter the user email address
3. Select the user role
4. Click <button class='button button--success button--ui button--nolink'>Add user</button>
5. Celebrate

Additionally, you can set up a user as a <kbd>Billing Contact (unlicensed)</kbd>. This is perfect for people who don't need to use GitKraken Client, but wish to have access to manage the account subscription and settings.



### Buying more licenses

First log into [https://app.gitkraken.com](https://app.gitkraken.com) and click through to <kbd><strong>Organization > [Your organization name] > Subscription</strong></kbd>.

Increase the user count and then complete the purchase. User upgrades are always prorated to your billing cycle.

<img src="/wp-content/uploads/buy-more-licenses.png" class="img-bordered img-responsive center">

<div class='callout callout--success'>
    <p>Do you have questions about upgrading your plan or an order? <a href="https://www.gitkraken.com/contact">Contact us</a></p>
</div>

### Removing users

To remove a user and free up a license, click <button class='button button--danger button--ui button--nolink'>Remove</button> next to the user on the list followed by <kbd>Remove User</kbd> for confirmation.

<img src="/wp-content/uploads/remove-user.png" srcset="/wp-content/uploads/remove-user.png" class="img-responsive center img-bordered">

### Reallocating licenses

Any `Owner`, `Admin`, or `Billing Contact` may remove users and then add users to reallocate licenses from [https://app.gitkraken.com](https://app.gitkraken.com). 

Note, `Billing Contact` roles cannot remove or edit `Owner` or `Admin` users. 

From the *Users* pane in the left panel, click to <button class='button button--danger button--ui button--nolink'>Remove</button> a user. Then click <button class='button button--success button--ui button--nolink'>Add User</button>.

<img src="/wp-content/uploads/licenses-page.png" srcset="/wp-content/uploads/licenses-page@2x.png 2x" class="img-responsive center img-bordered">

### Importing/Exporting users 

To import users click the `Add User` button. From here you can import users via a `.csv` file. 

<img src="/wp-content/uploads/account-site-import-button.png" class="img-responsive center img-bordered"/> 

When importing users, be sure to have columns for `Email`, `Username`, `Role`, `User License`.

If you need to export users, you may access this option from the Users list on [https://app.gitkraken.com](https://app.gitkraken.com).

<img src="/wp-content/uploads/account-site-export-arrow.png" class="img-responsive center img-bordered"/> 

The export will contain columns for `Email`, `Username`, `Role`, `User License`.

***
## Billing information
Review billing information or switch between credit card and Paypal at any time.

### Editing billing

To edit your billing or to switch payment methods, first log in as an `Admin` or the `Owner` and click <kbd><strong>Organization > [Your organization name]</strong></kbd>. 

Click **Subscription** to update the subscription.  From here you may select <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>Update Payment</span></button> to change your card details or switch payment methods.

<img src="/wp-content/uploads/edit-billing.png" class="img-bordered img-responsive center">

If you are switching from credit card to Paypal, follow the prompts to authenticate with Paypal.

### Looking for receipts or payment history?
Each billing cycle, our accounting system will send the owner listed a subscription a receipt for record keeping. The account site does not currently display billing history but please email [accounting@gitkraken.com](mailto:accounting@gitkraken.com) for additional copies.

***

## Transfer ownership

If you are the `Owner` of a <strong>GitKraken Pro</strong> or <strong>GitKraken Enterprise</strong> account, then you may transfer ownership to a different user from [https://app.gitkraken.com](https://app.gitkraken.com).

To transfer ownership, navigate to <kbd><strong>Organization > [Your organization name] > Settings</strong></kbd>. Then select the existing user who will become the new `Owner`.

<img src="/wp-content/uploads/transfer-ownership.png" class="img-responsive center img-bordered">


***
## Cancellations

To cancel, first log into your GitKraken account as the `Admin` or `Owner` and click <kbd><strong>Organization > [Your organization name] > Subscription</strong></kbd>.

You may then `Cancel Subscription` from the lower left corner.

Canceling will turn off the auto-renewal but you will retain access to your license(s) for the remainder of your subscription period. 

## Reactivate a subscription

Any canceled or expired subscription may be reactivated by logging into [https://app.gitkraken.com](https://app.gitkraken.com) as the `Owner`, `Admin` or `Billing Contact`.

Click on <kbd>Organizations</kbd> and then click on the name of the expired or canceled subscription.

<img src="/wp-content/uploads/org-expired.png" srcset="/wp-content/uploads/org-expired@2x.png 2x" class="img-responsive center img-bordered">

Then click on <kbd>Subscription</kbd> in the left panel, where you may update the license total or billing details before hitting <button class='button button--success button--ui button--nolink'>Reactivate</button>.
