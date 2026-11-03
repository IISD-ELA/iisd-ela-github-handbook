# Tutorial 5 — Maintaining your project through GitHub

&nbsp;&nbsp;&nbsp;Lastly, let's look at a few simple practices for keeping your repository organized and useful. You don't need to update your repository regularly or ever. Even if you only make changes once a year, or never again, these practices help ensure your work is understandable and accessible to fellow staff.

**1. Keep your README up to date**  
&nbsp;&nbsp;&nbsp;Your repository's `README.md` is often the first thing someone sees when opening your project. It should help others (and future you!) understand what the repository contains.

&nbsp;&nbsp;&nbsp;If you submitted your project through our automated submission system, you'll notice that the system has already created an initial `README.md` using the information you provided in your submission.

&nbsp;&nbsp;&nbsp;As your project evolves, consider updating it to reflect its purpose, contents, instructions, requirements, and status. You can edit your `README.md` directly through GitHub as covered in *Level 1 - Tutorial 3 - Editing and uploading files through GitHub*.

&nbsp;&nbsp;&nbsp;If you are unsure how to create or edit Markdown files (i.e., file extension `.md`), please refer to section [xyz](#xyz) for useful resources to get you started.

**2. Keep your files organized**  
&nbsp;&nbsp;&nbsp;Our automated submission system creates repositories using a standardized folder structure to help keep IISD-ELA projects organized and consistent. Once your project is uploaded by the system, you are free to adapt this structure to suit your project by removing unused folders, adding new folders or subfolders, and reorganizing files as needed.

&nbsp;&nbsp;&nbsp;For a detailed explanation of the ideal folder structure, file organization guidelines, and how to manage files such as .gitignore and .gitkeep, see [Appendix 2: IISD-ELA Repository Structure and File Guideline](../appendices/repository-structure.md#2-iisd-ela-repository-structure-and-file-guideline).

&nbsp;&nbsp;&nbsp;As you maintain your repository, try to use descriptive filenames and avoid keeping unnecessary duplicate versions of files. Since GitHub tracks changes automatically through commits, you generally don't need multiple files named `protocol_final_v2.md` or `analysis_FINAL_revised.R`.

**3. Make small, descriptive commits**  
&nbsp;&nbsp;&nbsp;When updating your repository, try to group related changes into separate commits and give each one a meaningful description.

For example:  
* *Updated lake sampling procedure for 2026*
* *Corrected units in fish calculation*
* *Added instructions for processing sensor data*

&nbsp;&nbsp;&nbsp;This makes it easier to understand your project's history and find previous versions.

**4. Keep your repository safe and accessible**  
&nbsp;&nbsp;&nbsp;Before adding or updating files:

* Check that you're not uploading passwords, API keys, personal information, or other sensitive material.
* Avoid uploading unnecessarily large datasets or files better suited to organizational storage or scientific data repositories.
* Make sure you have permission to share any third-party materials.
* Check whether your repository should remain private or whether it is appropriate for public access.

&nbsp;&nbsp;&nbsp;If you're unsure about permissions, visibility, or what belongs in your repository, contact the IISD-ELA Data team at iyaktubay@iisd-ela.org or eladata@iisd-ela.org. 

**5. Know when to move beyond the GitHub Website**  
&nbsp;&nbsp;&nbsp;For occasional updates to project files, working directly through the GitHub website (i.e., learning the skills covered in [Level 1](level-1.md#level-1-github-basics---working-in-your-browser)) may be all you need. However, if you frequently modify multiple files, work on larger projects, collaborate with others, or want to manage changes more efficiently, you may benefit from using Git through an application such as VS Code or RStudio (covered in Level 2).
