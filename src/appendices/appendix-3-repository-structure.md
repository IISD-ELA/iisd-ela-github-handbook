# 2. IISD-ELA Repository Structure and File Guideline

&nbsp;&nbsp;&nbsp;When you submit your project through our automated submission system, your repository will have the following structure by default, and your files will be uploaded to the appropriate folders. This helps keep IISD-ELA repositories organized and consistent. You are free to adapt this structure as needed by removing folders you don’t use, adding new folders and subfolders relevant to your project, and editing files like ```.gitignore```.

```
<your-repo-name>/       # ideally, the name should be all lower case, with each word separated by a hyphen
│
├── data/               # data inputs used directly in scripts (see more notes below)
|   ├── tracked-data/    # small, example datasets, not ignored by git (see more notes below)
│   └── ...             # optional subfolders; update this tree if added
├── docs/               # any relevant documentation
│   └── ...             # optional subfolders; update this tree if added
├── debug/              # scripts or files related to debugging
│   └── ...             # optional subfolders; update this tree if added
│
├── scripts/            # R, Python, other code
│   └── ...             # optional subfolders; update tree if added
├── results/            # figures, tables, and other outputs
|   ├── tracked-data/    # small, example output items, not ignored by git (see more notes below)
│   └── ...             # optional subfolders; update tree if added
│
├── src/                # reusable functions, modules, pipelines
│   └── ...             # optional subfolders; update tree if added
├── infra/              # infrastructure files
│   └── ...             # optional subfolders; update tree if added
├── config/             # parameters, constants, .yml files
│   └── ...             # optional subfolders; update tree if added
│
├── README.md           # this file, required
├── .gitignore          # list of files for git to ignore, required
└── LICENSE             # usage license, required (see more notes below)

```

&nbsp;&nbsp;&nbsp;The repo structure is organized here by usage: ```data/```, ```docs/```, ```debug/``` likely apply to all repos, but ```scripts/``` and ```results/``` may only be needed by research scientists. Similarly, ```src/```, ```infra/```, and ```config/``` may only be needed by the data team. The ```README.md``` and ```.gitignore``` files are required by all IISD-ELA repositories, whereas ```LICENSE``` is only required by public repositories.

#### Notes on Data Files
&nbsp;&nbsp;&nbsp;In most cases, you should *not* commit full, large datasets to the repository; these should remain on your local machine unless they are small, non-sensitive example datasets. To support this, common data file types are included in the .gitignore so that they are ignored by Git *by default*. However, an exception is made for the ```data/tracked-data/``` and ```results/tracked-data/``` directories, where example datasets and outputs *can* be committed. This is done using Git's negation rules (i.e., `!` patterns) in the `.gitignore`, so files like CSVs are ignored everywhere except inside these directories. If your project needs additional datasets to be tracked, you can adjust the `.gitignore` as needed.

#### Notes on Licenses for Public Repositories
&nbsp;&nbsp;&nbsp;Every public repository requires a license file. A license file tells others how they can use, share, or modify your code and documents. To add a license to your public repository:
1. Click **Add file > Create new file**
2. Name the license file: ```LICENSE``` (no file extension)
3. Click **"Choose a license template"**
4. Select a license (e.g., **MIT License** for simple, permissive use)
5. GitHub will automatically fill in the text with the current year and our organization
6. Scroll down and **Commit new file**.
7. Your repository now has an official license that lets other legally use and share your work.

&nbsp;&nbsp;&nbsp;For more information on licensing your repo, see [GitHub's official documentation](https://can01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.github.com%2Fen%2Frepositories%2Fmanaging-your-repositorys-settings-and-features%2Fcustomizing-your-repository%2Flicensing-a-repository&data=05%7C02%7Ciyaktubay%40iisd-ela.org%7C36b4f87e16ac4024f93408de37377ccc%7C01a20ec6cfd9471cb34bedc36161c3ce%7C0%7C0%7C639008908684459389%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=cdmjoNz8Z%2BwbCw0MGbWcQeFuhEsAAQ%2BM2HEngarFMEc%3D&reserved=0).

#### Notes on .gitkeep
&nbsp;&nbsp;&nbsp;The folders in your repository will each contain a file called ```.gitkeep```, which tells git to keep the empty folders in the repository (otherwise they get automatically excluded). You can safely delete ```.gitkeep``` once you add your own files to a folder.
