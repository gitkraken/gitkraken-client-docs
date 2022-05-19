---

title: GitKraken Boards
description: Integrate GitKraken Client with your GitKraken Boards for easy task tracking.
taxonomy:
    category: gitkraken-client

---

<div class='callout callout--danger'>
    <p> GitKraken Boards and GitKraken Timelines will sunset at the end of 2022. Please read our <a href="https://www.gitkraken.com/boards-and-timelines" target="_blank">full anouncement and FAQ</a> to learn more. </p>
</div>

GitKraken Boards is the only issue board for task and issue tracking that is fully integrated with GitKraken Client.

***


## Connect GitKraken Boards Integration

Set up the integration from the ISSUES pane in the left panel or from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Integrations</i></kbd>.

<img src="/wp-content/uploads//choose-boards.png" srcset="/wp-content/uploads//choose-boards@2x.png" class="img-bordered img-responsive center">

Select GitKraken Boards and you will automatically connect.

### Switching Issue Trackers

You may easily switch between issue trackers for a given repo from <kbd><i>Preferences    <i class='fa fa-caret-right'></i>     Issues</i></kbd>.

<img src="/wp-content/uploads//switch.png" srcset="/wp-content/uploads//switch@2x.png" class="img-bordered img-responsive center">

### Preview Cards

Once connected, your GitKraken Board cards will start to appear in the left panel. The app will default to an <kbd>All cards</kbd>, <kbd>My Cards</kbd>, and <kbd>Unassigned cards</kbd> filters.

<img src="/wp-content/uploads//board-left.png" srcset="/wp-content/uploads//board-left@2x.png" class="img-bordered img-responsive center">

Hover over any card to get a preview of the card Title, Description, Column, Milestone, and Assignee.

<img src="/wp-content/uploads//preview.png" srcset="/wp-content/uploads//preview@2x.png" class="img-bordered img-responsive center">

### View Card Details

Click a card name from the left panel to view the card's details.

<img src="/wp-content/uploads//card-details.png" srcset="/wp-content/uploads//card-details@2x.png" class="img-bordered img-responsive center">

Here you may view and edit:

 - Title and Description
 - Column
 - Assignee
 - Add comments

Milestone and Due Date are also viewable but not editable.

Any changes made here will be reflected in your GitKraken Board.

### Create New Card

From the left panel, click the <button class='button button--success button--ui button--nolink'>+</button> icon to add a new card.

<img src="/wp-content/uploads//create-card.png" srcset="/wp-content/uploads//create-card@2x.png" class="img-bordered img-responsive center">

Your new card will automatically sync with your GitKraken Board.

### Create Filters

You may create filters to view the cards you need.

Read more about [filtering GitKraken Boards](/boards/filter-syntax/).

### Create Branches from Card

You may create a branches tied to a card from the card details view.

<img src="/wp-content/uploads/create-branch.gif" class="img-bordered img-responsive center">

The branch name will automatically prefill based on the card name. After the branch is created, these branches will be denoted with the boards icon to reflect its link to a card.


### Copy Card link

Click the <kbd> <i class="fa fa-ellipsis-v"></i> </kbd> icon to copy the card link or view the item directly in GitKraken Boards.

<img src="/wp-content/uploads//dots.png" srcset="/wp-content/uploads//dots@2x.png" class="img-bordered img-responsive center">


## Default board

GitKraken Client allows you to set a default GitKraken Board from this dropdown menu.

<img src="/wp-content/uploads//glo-board.png" srcset="/wp-content/uploads//glo-board@2x.png 2x" class="img-responsive center img-bordered">

This will allow you to immediately open this default board when you click the `Boards` button.

<img src="/wp-content/uploads//glo-board.gif" class="img-responsive center img-bordered">


Each repo can have its own default board, so be sure to give this a try!

## Associate issues to Pull Requests

Link cards to <a href="/working-with-repositories/pull-requests/#glo-cards">pull requests</a> in GitKraken Client to automate issue mananagement after setting up <a href="/glo/board-features/#pull-requests">GitHub pull request integration</a> on your GitKraken Board.

Associating a card to a pull request is easy; simply search for the card name while creating a pull request.

<img src="/wp-content/uploads//glo-pr.gif" class="img-responsive center img-bordered">


In GitKraken Boards, the card details panel will populate with the pull request information created in GitKraken Client.

<img src="/wp-content/uploads//glo-gk-pr.png" srcset="/wp-content/uploads//glo-gk-pr@2x.png 2x" class="img-responsive center img-bordered">

## Remove GitKraken Boards from the toolbar

To remove Boards from the toolbar navigate to <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> UI Preferences</em> and uncheck _Show Boards button in toolbar_.

[Learn more](/glo/start-glo-ing) about GitKraken Boards.
***
