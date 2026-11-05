# Level 2 - Tutorial 6 - Viewing history and undoing changes

&nbsp;&nbsp;&nbsp;To reiterate, one of Git's biggest advantages is that it keeps a record of your project's development. Every commit creates a checkpoint that you can revisit to see what changed, compare versions, or recover earlier work.

### 1. Viewing your commit history on VS Code and RStudio
&nbsp;&nbsp;&nbsp;On VS Code, open the **Source Control** panel and look for the repository's commit history. You can select previous commits to inspect changes. The exact interface may vary depending on your VS Code version and installed extensions.

&nbsp;&nbsp;&nbsp;On RStudio, open your project and navigate to the **Git** tab, click **History**, and select a commit to review its details and file changes.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/4lnVp8yG5MY"
  title="viewing commit history on rstudio and vscode"
  allowfullscreen>
</iframe>


### 2. Undoing Changes
&nbsp;&nbsp;&nbsp;Git provides several ways to undo mistakes, depending on whether you've committed your changes.

#### Discarding Uncommitted Changes
&nbsp;&nbsp;&nbsp;If you've edited a file but haven't committed those changes, you can restore the file to its last committed version. In RStudio or VS Code, find the modified file in the Git/Source Control interface and select the option to **Revert** or **Discard Changes**. See below video for a demo.

***Discarding uncommitted changes can permanently delete your edits. Make sure you no longer need them before proceeding.***

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/NbfqTD91XKs"
  title="discarding uncommitted changes on rstudio and vscode"
  allowfullscreen>
</iframe>

#### Undoing an Existing Commit
&nbsp;&nbsp;&nbsp;If you've already committed changes, you can use Git's **Revert** operation to create a new commit that reverses an earlier one. Unlike deleting or rewriting history, reverting preserves the original commit and records the reversal as a new change. For beginners, this is generally the safer approach, especially when a commit has already been pushed to GitHub. For step-by-step instructions, see [GitHub Docs - Reverting a commit](https://docs.github.com/en/desktop/managing-commits/reverting-a-commit-in-github-desktop). 

&nbsp;&nbsp;&nbsp;See below video for a demo using VS Code and the GitHub website.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/606zSGhzySg"
  title="reverting commits on vscode"
  allowfullscreen>
</iframe>

### 3. Good Practices

* Write descriptive commit messages so you can easily identify earlier changes.
* Review the differences before discarding or reverting anything.
* Avoid rewriting or deleting shared commit history, particularly when collaborating with others.
* Commit regularly so you have useful checkpoints to return to.