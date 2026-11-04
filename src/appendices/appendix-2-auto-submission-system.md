# IISD-ELA GitHub Project Submission System
&nbsp;&nbsp;&nbsp;Creating a repository on GitHub is relatively easy, even for someone who has never used GitHub before. However, ensuring that each repository follows our [organization-specific guidelines](appendix-1-repo-creation.md) -including naming conventions, documentation, folder structure, topic tags, and permissions- requires additional steps.  

&nbsp;&nbsp;&nbsp;Our automated GitHub Project Submission System was developed to handle all of these steps automatically, removing obstacles for staff who want to contribute projects but are afraid it would take too much time and effort.

&nbsp;&nbsp;&nbsp;Importantly, **the system allows staff to contribute their work without needing to interact with GitHub at all**. This helps make contributing to our GitHub accessible to everyone, *especially those who have no interest in using it beyond the initial submission*. For those who are interested in further developing their projects after the initial submission, this handbook is intended as a comprehensive resource.

## How does it work?

1. Following [simple instructions](https://docs.google.com/document/d/1eCa5YFolbrqcge32kDppIOliPDPeAORpq9xa0qv4u8g/edit?usp=drive_link), upload your project files to the [designated Google Drive folder](https://drive.google.com/drive/folders/1x922EzeZKErssw4pwZXoaOc-TPY5olu7?usp=drive_link) and complete a copy of the project information form.
2. Every night, the system will check for new submissions and create repositories under the IISD-ELA GitHub.
3. The system will create your repository following [our repository guidelines](appendix-1-repo-creation.md) based on the information you submitted in the project form.
4. Once your repository is ready, you will receive an *email* containing a link to it, along with a link to this handbook for resources in case you choose to continue developing your project.

&nbsp;&nbsp;&nbsp;**That's really it**. Your project now lives within the IISD-ELA GitHub organization, whether or not you want to continue working on it.

## Technical System Documentation
&nbsp;&nbsp;&nbsp;The system was built using Python, AWS, and GitHub and Google Drive APIs. Its source code and technical documentation are maintained in the private repository: [IISD-ELA/automate-repository-creation](https://github.com/IISD-ELA/automate-repository-creation).

&nbsp;&nbsp;&nbsp;Understanding the technical implementation is probably only useful for the IISD-ELA data team. However, if you're curious, you can explore the repository if you already have access. Or, you can contact me to request access (iyaktubay@iisd-ela.org).