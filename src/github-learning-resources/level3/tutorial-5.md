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
