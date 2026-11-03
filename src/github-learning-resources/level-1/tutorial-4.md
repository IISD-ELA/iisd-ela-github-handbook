# Tutorial 4 — Understanding commits and version history

&nbsp;&nbsp;&nbsp;We already covered how to navigate to your repository's commit history in *Level 1 - Tutorial 2 -  Understanding our GitHub Repositories*. This tutorial goes a bit deeper by teaching you *how to view what changed in a commit*, *how to view an earlier version of a file*, and *how to restore your repository to an earlier version*.

**1. Viewing what changed in a commit**  
&nbsp;&nbsp;&nbsp;You can examine exactly what was modified in a particular commit.
1. From the commit history, click a commit message.
2. Github displays the changes made in that commit.
3. Added lines are highlighted in **green**, while removed lines are highlighted in **red**.

**Example:** You updated an IISD-ELA data info sheet several times throughout the year. By reviewing previous commits, you can identify when a particular step was introduced or modified. See changes in the IISD-ELA chemistry info sheet, for instance: 

 
<kbd>
    <img src="../media/level1-tutorial4-1.png" alt="IISD-ELA GitHub homepage" width="50%"> 
</kbd>

<kbd>
    <img src="../media/level1-tutorial4-2.png" alt="IISD-ELA GitHub homepage" width="200%"> 
</kbd>


**2. Viewing an earlier version of a file**  
&nbsp;&nbsp;&nbsp;You can also look at the history of an individual file rather than an entire repository.

1. Open the file you're interested in.
2. Click **history** (you'll find it in the file's three-dot menu).
3. Select a previous commit to view the file's changes at that point.
4. To see the complete earlier version, open the file as it existed at that commit.

This lets you compare earlier versions without changing your current files.

<kbd>
    <img src="../media/level1-tutorial4-3.png" alt="IISD-ELA GitHub homepage" width="200%"> 
</kbd>

<kbd>
    <img src="../media/level1-tutorial4-4.png" alt="IISD-ELA GitHub homepage" width="200%"> 
</kbd>

**3. Recovering an earlier version**  
&nbsp;&nbsp;&nbsp;If you've accidentally changed or deleted something, or simply want to undo your changes, you can often recover it using GitHub's version history.

&nbsp;&nbsp;&nbsp;For a simple commit with only one affected file:
1. Find the earlier version you want to recover using the file's history.
2. Open that version and select **Raw** to view its contents.
3. Copy the contents.
4. Return to the current version of the file and click the **pencil icon** to edit it.
5. Replace the contents with the earlier version and commit the change with a descriptive message such as "Restored previous version of sampling info sheet".

&nbsp;&nbsp;&nbsp;This creates a **new commit** containing the restored content. It doesn't erase your previous commits or history. ***For more complex changes involving multiple files, contact the IISD-ELA Data team for assistance at*** (iyaktubay@iisd-ela.org ***or*** eladata@iisd-ela.org).
