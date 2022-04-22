---

title: Git integration for Jira
description: GitKraken and Git Integration for Jira working together
taxonomy:
    category: gitkraken-client

---

GitKraken connects with the <a href="https://marketplace.atlassian.com/apps/4984/git-integration-for-jira" target="_blank">Git Integration for Jira</a> app, which provides seamless navigation between GitKraken Git Client and Jira when viewing commit and file diffs related to Jira issues. 

### How to connect

To use this integration, you first need to:

* Connect  <a href="/integrations/jira">Jira Cloud Integration</a> in GitKraken
* Select  <a href="/integrations/jira/#connect-jira-integration">Jira Cloud as the Issue Tracker</a> for a repository <em class='context-menu'>Preferences <i class='fa fa-caret-right'></i> Issue Tracker</em>
* Select a Jira Project in the left panel
* Git Integration for Jira must be installed on the same Jira Cloud instance

---

### Open File Diff in Jira from GitKraken

Once connected to a Jira Project, the <button class='button button--primary button--ui button--nolink'><span style='color:#141422;'>Open in Jira</span></button> button will become available from the file diff view. 


<img src="/img/documentation/integrations/git-integration-for-jira/gk-to-gij-button.png" class="img-responsive center img-bordered">


### Open Jira to a commit from GitKraken

Once connected to a Jira Project, right-click on a commit in the graph to access the option to open the commit in your Jira instance. 

<img src="/img/documentation/integrations/git-integration-for-jira/gk-to-gij-right-click-drop-down.png" class="img-responsive center img-bordered">

This provides a quick link for opening Jira with the target commit already in focus.

---

### Open GitKraken from the Git Integration for Jira

It's easy to dive deeper into your commits and branches. Within the Git Integration for Jira, the commits and diffs will have links to open in GitKraken - just look for Keif <i class="fab fa-gitkraken"></i> !

<img src="/img/documentation/integrations/git-integration-for-jira/gij-to-gk-button-2.png" class="img-responsive center img-bordered">