# Level 3 - Tutorial 3 - Creating and pull requests
&nbsp;&nbsp;&nbsp;In the previous tutorial, you learned how to create branches and make changes without affecting your repository's `main` branch. Once you're satisfied with your changes, you can propose incorporating them into `main` by creating a ***pull request (PR)*** on GitHub, so that other contributors can review your changes before merging with `main`.

### 1. What is a pull request?
&nbsp;&nbsp;&nbsp;A pull request is a way to propose changes from one branch to another. It allows you and your collaborators to review, discuss, and approve changes before merging them. Pull requests also provide a record of what was changed, why, and any discussions or decisions made before merging.

### 2. Creating a pull request on GitHub
&nbsp;&nbsp;&nbsp;Before creating a pull request, ***make sure you've committed and pushed your changes to your branch on GitHub***.

1. Open your IISD-ELA repository on GitHub.
2. Navigate to the ***Pull requests***tab and click ***New pull request***.
3. Select the branches you want to compare:
    * **Base:** main (the branch you want to merge changes into).
    * **Compare:** Your working branch (e.g., `update-temperature-calculations`).
6. Review the changes shown and click ***Create pull request***.
7. Enter a descriptive title and a brief explanation of your changes.
8. Click ***Create pull request*** to submit it.

&nbsp;&nbsp;&nbsp;GitHub may also display a ***Compare & pull request*** button after you push a new branch, which takes you directly to the pull request creation page.

<iframe
  width="100%"
  height="400"
  src=""
  title="Pulling from a remote repo - VS Code"
  allowfullscreen>
</iframe> **add this video once uploads**

 ### 3. What Happens After Creating a Pull Request?
&nbsp;&nbsp;&nbsp;Once you've opened a pull request, collaborators can:
1. Review the proposed changes.
2. Leave comments or ask questions.
3. Suggest improvements.
4. Approve the changes before they're merged.

&nbsp;&nbsp;&nbsp;Creating a pull request does not automatically change main. Your changes remain on your working branch until the pull request is merged. You can also continue making commits to the same branch. When pushed to GitHub, these additional commits will automatically appear in the existing pull request.