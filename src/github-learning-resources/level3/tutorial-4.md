# Level 3 - Tutorial 4 - Reviewing and merging pull requests
&nbsp;&nbsp;&nbsp;In the previous tutorial, we looked at how to create a pull request to propose changes to your repository's `main` branch. We also briefly looked at how to merge a pull request in the [video tutorial](tutorial-3.md#2-creating-a-pull-request-on-github). In this tutorial, we will look more closely at reviewing proposed changes, providing feedback, and merging pull requests once they're ready.

### 1. Reviewing a pull request
&nbsp;&nbsp;&nbsp;When someone opens a pull request, other collaborators can review the proposed changes before they're incorporated into the main project. To review a pull request:
1. Open your repository on GitHub.
2. Navigate to the ***Pull requests*** tab.
3. Select the pull request you want to review.
4. Open the ***Files changed*** tab to see which files were modified and compare their contents.

&nbsp;&nbsp;&nbsp;GitHub highlights added lines in green and removed lines in red, making it easier to identify exactly what has changed.

### 2. Leaving comments and reviews
&nbsp;&nbsp;&nbsp;If you have questions or suggestions about someone's changes, you can leave comments directly on the pull request. In the ***Files changed*** tab, hover beside a line of code and click the `+` icon to add a comment.

&nbsp;&nbsp;&nbsp;You can also submit a formal review by selecting ***Review changes***, with three possible outcomes:
* ***Comment:*** Provide feedback without explicitly approving or rejecting the changes.
* ***Approve:*** Indicate that you've reviewed the changes and they're ready to merge.
* ***Request changes:*** Indicate that something should be addressed before merging.

### 3. Responding to Feedback
&nbsp;&nbsp;&nbsp;If someone requests changes to your pull request, you can continue editing your working branch. Simply make the necessary changes, commit them, and push them to GitHub, just as you learned in [Level 2](../level-2.md).

&nbsp;&nbsp;&nbsp;*Any new commits pushed to the same branch will automatically appear in the existing pull request. You don't need to create another one.*

### 4. Merging a Pull Request
&nbsp;&nbsp;&nbsp;Once the changes have been reviewed and are ready to incorporate, you can merge the pull request into main.
1. Open the pull request on GitHub.
2. Confirm that the proposed changes are correct and any required reviews or checks have passed.
3. Click Merge pull request (if available).
4. Confirm the merge.

&nbsp;&nbsp;&nbsp;GitHub will incorporate the changes into main, making them part of the primary version of your repository.

*&nbsp;&nbsp;&nbsp;Your ability to merge may depend on your repository permissions and any branch protection rules.*

#### What Happens to Your Branch After Merging?
&nbsp;&nbsp;&nbsp;After merging, GitHub may offer a ***Delete branch*** button. You can safely delete the working branch if its changes have been merged and you no longer need it. This helps keep your repository organized.

&nbsp;&nbsp;&nbsp;*However, deleting the branch on GitHub does not automatically delete any local copy you may have in RStudio or VS Code.*

### 6. Updating Your Local Repository
&nbsp;&nbsp;&nbsp;After merging a pull request, your local main branch may not yet contain the newly merged changes. To update it:
1. Open your repository in RStudio or VS Code.
2. Switch to the main branch.
3. Pull the latest changes from GitHub.

&nbsp;&nbsp;&nbsp;Your local main branch should now include the changes from the merged pull request.

### 7. Reviewing and merging pull requests - video demo