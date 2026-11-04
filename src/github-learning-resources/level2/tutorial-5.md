# Level 2 - Tutorial 5 - Pulling changes from GitHub

&nbsp;&nbsp;&nbsp;In the previous tutorial, we learned that **committing saves changes locally**, while **pushing** (i.e., "**sync**" on VS Code and RStudio) uploads those commits to GitHub.
&nbsp;&nbsp;&nbsp;But what happens when changes are made directly on GitHub, or when someone else updates your repository? To bring those changes onto your local computer, you need to **pull**.

### 1. Understanding a "pull"
&nbsp;&nbsp;&nbsp;Pulling downloads the latest changes from GitHub and integrates them into your local repository. For example, someone might update a script, fix an error, or add documentation to your repository through GitHub. Those changes won't automatically appear in the cloned folder on your computer. **Pulling keeps your local repository up to date with the version on GitHub.**

### 2. When should you pull?
&nbsp;&nbsp;&nbsp;As a general habit, pull before starting a new work session, particularly if other people have access to your repository.  
&nbsp;&nbsp;&nbsp;You should also pull after making changes directly through the GitHub website or when you know a collaborator has pushed new commits.

### 3. What if there are conflicting changes?
&nbsp;&nbsp;&nbsp;If you have uncommitted local changes, Git may prevent a pull if the incoming changes would overwrite them. This usually happens when you or another person edit the same part of a file, which creates a **merge conflict**. We will cover merge conflicts in **Level 3: Collaboration - working with others**.

### 4. How to pull changes using VS Code
&nbsp;&nbsp;&nbsp;The following video shows how to "pull" changes from a remote GitHub repository, using a collaborative IISD-ELA repository as an example, on VS Code.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/XQsXb7_Zljc"
  title="Pulling from a remote repo - VS Code"
  allowfullscreen>
</iframe>

### 5. How to pull changes using RStudio
&nbsp;&nbsp;&nbsp;The following video shows how to "pull" changes from a remote GitHub repository, using a IISD-ELA repository where changes were made directly on the GitHub website, on RStudio.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/ByU8yXpBhII"
  title="Pulling from a remote repo - RStudio"
  allowfullscreen>
</iframe>
