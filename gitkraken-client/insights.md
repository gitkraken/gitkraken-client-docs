---

title: Insights
description: GitKraken Insights is a powerful tool that helps you visualize how pull requests are merged into your repositories.
taxonomy:
    category: gitkraken-client

---

### What is GitKraken Insights?

GitKraken Insights is a powerful tool that helps you visualize how pull requests are merged into your repositories. It provides a visual representation of your repository's history, allowing you to see how your codebase has evolved over time. You can use this information to make informed decisions about how to improve your workflow.

Insights is available for Github.com, Bitbucket.org, and Gitlab.com.

<img src="/wp-content/uploads/Insights.png" class="img-responsive center img-bordered">

<div class='callout callout--warning'>
    <p>
        <strong>Note:</strong> Insights is in Preview mode, and we'd love to hear your thoughts and feedback. Just click on the "Provide feedback on this view" prompt in the upper left of the Pull Requests page to tell us what you think.
    </p>
</div>

### How do I use GitKraken Insights?

To enable GitKraken Insights, you’ll first need to open a Cloud Workspace and then navigate to the Pull Request section. From here, click to connect to your remote hosting service.

<img src="/wp-content/uploads/insights-connect.png" class="img-responsive center img-bordered">

You can also connect Gitkraken Insights to your remote hosting service from <kbd>Preferences > Integrations</kbd>

<img src="/wp-content/uploads/insights-connect-integration.png" class="img-responsive center img-bordered">

### Metrics

<img src="/wp-content/uploads/insights-metrics.png" class="img-responsive center img-bordered">

Once you've connected to your remote hosting service, you'll be able to see the following metrics:

* **Cycle Time**: Measures the average time it takes for a pull request to be merged for the selected timeframe.
* **Average Throughput**: Measures the average number of pull requests merged for the selected timeframe. 
* **Merge** Rate: The percentage of merged pull requests compared to open pull requests for the selected timeframe. 
* **Open**: The total number of pull requests opened for the selected timeframe.
* **Merged**: The total number of pull requests merged for the selected timeframe.

You can see the metrics for the last 7 or 14 days (only available for Cycle Time and Average Throughput).

The <i class="fa-solid fa-circle-info"></i> icon will provide information about the metric.

<img src="/wp-content/uploads/insights-metrics-info.gif" class="img-responsive center img-bordered">