---

title: Pull request filters
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b> <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.19+</b>

This feature allows administrators to hide pull requests and branches based on a filter/regex. The Git Integration for Jira app supports integration or repository level filter.

The PR filter is available on the following locations:

1.  **Integration Feature Settings page** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Edit integration feature settings

    ![Pull request filter location 1](/wp-content/uploads/gij-gitserver-pr-hide-filter-location-01.png)

2.  **Update Repository page (integration sub repository)** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Show integration repositories

    ![Pull request filter location 2](/wp-content/uploads/gij-gitserver-pr-hide-filter-location-02.png)

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The PR filter is not available on the following locations:
        <ul style='margin-bottom:0px'>
            <li>Update Repository page for plain repository – <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit repository settings.</li>
            <li>Update Repository page for repositories belonging to a tracked folder – <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit repository settings.</li>
        </ul>
    </div>
    </div>
</div>

&nbsp;

### Basic regex examples

*   The `prHideFilter` will hide PR starting with word/phrase "\[mq-bot\]", e.g. "\[mq-bot\] This is a test Pull Request".

    `^[mq-bot].*`

*   The `prHideFilter` will hide PR starting with word/phrase "Test" or "test", e.g. "Test Pull Request".

    `^(Test|test).*`

&nbsp;

### More advanced examples

For the example list of PRs (or MRs): TEST-1 pr\_1, TEST-1 pr\_2, TEST-1 pr\_23, TEST-1 pr\_3, TEST-1 pr\_4 – the following expressions can be used:

| Action | RegExp | Hide result | PR list result |
| :--- | :--- | :--- | :--- |
| Hide all PRs | .* | all | _none_ |
| Hide only **TEST-1 pr\_1** | `((^|, )(TEST-1 pr_1))+$` | TEST-1 pr\_1 | TEST-1 pr\_2<br>TEST-1 pr\_23<br>TEST-1 pr\_3<br>TEST-1 pr\_4 |
| Hides anything that does NOT contain the **TEST-1 pr\_2** phrase | `^((?!TEST-1 pr_2).)*$` | TEST-1 pr\_1<br>TEST-1 pr\_3<br>TEST-1 pr\_4 | TEST-1 pr\_2<br>TEST-1 pr\_23 |
| Hide all PRs **BUT** **TEST-1 pr\_2** | `^((?!((^|, )(TEST-1 pr_2))+$).)*$` | TEST-1 pr\_1<br>TEST-1 pr\_23<br>TEST-1 pr\_3<br>TEST-1 pr\_4 | TEST-1 pr\_2 |
| Hide some PRs: **TEST-1 pr\_1**, **TEST-1 pr\_2**, **TEST-1 pr\_3** | `((^|, )(TEST-1 pr_[1-3]))+$` | TEST-1 pr\_1<br>TEST-1 pr\_2<br>TEST-1 pr\_3 | TEST-1 pr\_23<br>TEST-1 pr\_4 |

