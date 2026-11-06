# Level 3 - Tutorial 5 - Resolving merge conflicts
&nbsp;&nbsp;&nbsp;When multiple people work on the same repository, Git can usually combine their changes automatically. However, sometimes Git encounters changes that it cannot combine on its own. This is called a ***merge conflict***. Merge conflicts are a normal part of a collaborative project and can be resolved by manually reviewing the conflicting changes and deciding what to keep.

### 1. What causes a merge conflict?
&nbsp;&nbsp;&nbsp;A merge conflict commonly occurs when two people modify the same lines of a file on different branches. For example, imagine two scientists working on the same R script:  
* ***Researcher A*** changes a calculation to exclude missing values.
* ***Researcher B*** modifies the same calculation to use a different filtering method.

&nbsp;&nbsp;&nbsp;When Git attempts to combine their branches, it may not know which version to keep. So, instead of choosing automatically, Git flags the conflict so someone can manually review and resolve it.

### 2. Identifying merge conflicts
&nbsp;&nbsp;&nbsp;You might encounter merge conflicts when:
* Pulling changes from GitHub into your local repository
* Merging one branch into another
* Attempting to merge a pull request on GitHub

&nbsp;&nbsp;&nbsp;Git will tell you which files contain conflicts and require attention.

### 3. Resolving merge conflicts in VS Code
&nbsp;&nbsp;&nbsp;VS Code provides a visual interface for comparing conflicting changes and choosing how to combine them. If you encounter a conflict locally on VS Code:

1. Navigate to the ***source control*** panel and locate the files marked as conflicted.
2. Open a conflicted file. VS Code may display its ***merge editor***, allowing you to compare the incoming and current changes.
3. Review the conflicting sections and choose whether to:
    * ***Accept current:*** Keep the changes from your current branch.
    * ***Accept incoming:*** Keep the changes being merged into your branch.
    * ***Accept both:*** Keep both sets of changesm, where appropriate.
    * ***Edit manually:*** Combine or rewrite the changes yourself.
4. Review the resulting file and save it.
5. Mark the conflict as resolved, stage the file, and complete the merge by committing if Git requires it.

&nbsp;&nbsp;&nbsp;Here is a video demo on resolving conflicts in VS Code.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/vBHUZoqo6jI"
  title="Pulling from a remote repo - VS Code"
  allowfullscreen>
</iframe> 

### 4. Resolving merge conflicts in RStudio
&nbsp;&nbsp;&nbsp;RStudio provides a graphical interface for common Git operations, such as committing, pushing, pulling, and creating branches. However, it does not have a dedicated graphical interface for merging branches or resolving merge conflicts, unlike VS Code. If you encounter a merge conflict while pulling changes in RStudio:
1. Open the Git tab to identify which files have conflicts.
2. Open the affected files and look for Git's conflict markers (`<<<<<<<`, `=======`, and `>>>>>>>`).
3. Carefully edit the files to keep the correct changes, removing the conflict markers.
&nbsp;&nbsp;&nbsp;Save your changes, stage the resolved files, and complete the merge commit if required.

&nbsp;&nbsp;&nbsp;While you can manually edit conflicting files in RStudio, initiating branch merges and some conflict-resolution steps require using Git commands in the Terminal. For this reason, we strongly recommend using VS Code for merging branches and resolving conflicts, even if you normally develop your R projects in RStudio. You can open the same local repository in VS Code without affecting your RStudio project.

&nbsp;&nbsp;&nbsp;If you're interested in using Git through the command line, see [Atlassian's Git Merge Conflict Tutorial](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) for additional explanations and examples.

### 5. Resolving conflicts on GitHub
&nbsp;&nbsp;&nbsp;For certain simpler conflicts, GitHub allows you to resolve them directly through a pull request.
1. Open the pull request containing the conflict.
2. Click ***Resolve conflicts***, if available.
3. Review the conflicting sections of the file.
4. Edit the content to produce the correct final version, removing Git's conflict markers.
5. Click ***Mark as resolved*** and then ***Commit merge***.

&nbsp;&nbsp;&nbsp;If the conflict is too complex for GitHub's web editor, you'll need to resolve it locally using Git, ideally with a tool like VS Code.

&nbsp;&nbsp;&nbsp;Here is a video demo on resolving a simple merge conflict on the GitHub website.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/p8vA2Eli_qk"
  title="Pulling from a remote repo - VS Code"
  allowfullscreen>
</iframe> 

### 6. Avoiding Merge Conflicts
&nbsp;&nbsp;&nbsp;Although conflicts can't always be prevented, a few good practices can reduce how often they occur:
* Pull regularly to keep your local repository up to date.
* Coordinate with other collaborators when working on the same files.
* Keep branches focused on specific tasks rather than making many unrelated changes.
* Merge completed work regularly rather than leaving branches separate for long periods.
* Review changes carefully before merging to ensure nothing important is lost.