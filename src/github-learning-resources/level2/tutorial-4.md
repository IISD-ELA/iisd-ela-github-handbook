# Level 2 - Tutorial 4 - Making changes and committing locally
&nbsp;&nbsp;&nbsp;Now that you've cloned your repository, you can edit its files directly on your computer using VS Code, RStudio, or other software. Git allows you to track your changes and save checkpoints (commits) as you work, without needing to upload anything to GitHub yet.

### 1. Understanding the Git workflow
&nbsp;&nbsp;&nbsp;When working locally, there are three basic steps:
1. **Modify:** Edit, add, or delete files in your project and save them.
2. **Stage:** Select which changes you want to include in your next commit.
3. **Commit:** Save those staged changes as a checkpoint in your local repository.  

&nbsp;&nbsp;&nbsp;*Committing changes locally does not automatically upload them to GitHub. You would still need to sync changes to ensure that your changes are uploaded. See below videos for more information.*

### 2. Making commits in VS Code
&nbsp;&nbsp;&nbsp;The following video shows how to make and review changes, stage files, create commits, and sync with the remote GitHub repository using an IISD-ELA repository as an example.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/OP8Cfj72Bys"
  title="Making Changes and Committing Locally - VS Code"
  allowfullscreen>
</iframe>

### 3. Making commits in RStudio
&nbsp;&nbsp;&nbsp;The following video shows how to make and review changes, stage files, create commits, and sync with the remote GitHub repository using an IISD-ELA repository as an example.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/ItU5AtWl4dw"
  title="Making Changes and Committing Locally - RStudio"
  allowfullscreen>
</iframe>

### 4. Understanding .gitignore
&nbsp;&nbsp;&nbsp;If you used [our automatic submission system](../../appendices/appendix-2-auto-submission-system.md) or if you manually created your repository following [our guidelines](../../appendices/appendix-1-repo-creation.md), then your repository already includes a `.gitignore` file, which tells Git which files and folders it should ignore.

&nbsp;&nbsp;&nbsp;For example, temporary files, local configuration files, files with sensitive information, and certain data files may be excluded from version control. In addition, you should always review your staged files to make sure you're not accidentally including sensitive information or unnecessarily large datasets. 

&nbsp;&nbsp;&nbsp;For details on our default `.gitignore` configuration and designated `tracked-data/` folders, see [Appendix 3 - IISD-ELA Repository Structure and File Guideline](../../appendices/appendix-3-repository-structure.md).

&nbsp;&nbsp;&nbsp;Below is a video explaining `.gitignore` files using an IISD-ELA GitHub repository as an example.

<iframe
  width="100%"
  height="400"
  src="https://www.youtube.com/embed/gj4Dw8TeXec"
  title="Understanding .gitignore files"
  allowfullscreen>
</iframe>