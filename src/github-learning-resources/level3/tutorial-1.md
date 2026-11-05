# Level 3 - Tutorial 1 - Introduction to collaborating with Git
&nbsp;&nbsp;&nbsp;When multiple people contribute to the same GitHub project, it's important to coordinate changes so that everyone's work can be incorporated without accidentally overwriting or interfering with each other's progress. Git and GitHub provide several features to make this easier.

## 1. Key collaboration concepts

There are three main concepts we'll focus on throughout this level:
| Concept | Explanation |
|---|---|
| *branches* | Separate lines of development that allow you to work on changes without immediately affecting the main version of a project |
| *pull requests* | A way to propose changes from one branch to another, allowing collaborators to review and discuss them before they're incorporated. |
|*merging* | The process of combining changes from different branches into one. |

## 2. Understanding the Main branch
&nbsp;&nbsp;&nbsp;Most repositories have a default branch called `main`, which represents the primary version of the project. In [Level 2](../level-2.md) tutorials, we were making commits to the `main` branch. However, for collaborative projects, it's  better to create separate branches for individual changes and merge them into `main` once they're ready. This keeps the `main` branch stable while collaborating.

## 3. A Typical collaborative workflow
1. ***Pull*** the latest changes from GitHub to your local computer (see [Level 2 - Tutorial 5](../level2/tutorial-5.md)).
2. Create a ***branch*** for the work you want to do.
3. Make and ***commit*** changes on your branch.
4. ***Push*** your branch to GitHub.
5. Open a ***pull request*** to propose merging your changes into `main`.
6. Review and ***merge*** the pull request once the changes are ready.

## 4. Do you need to use branches and pull requests?
&nbsp;&nbsp;&nbsp; Most of the time, no. If you're the only person working on a repository, the simpler workflows covered in [Level 2](../level-2.md) is really all you need. Even when collaborating, branches and pull requests aren't mandatory for every small change. However, they're strongly recommended when multiple people are actively developing the same project, particularly when changes need to be reviewed before being incorporated.