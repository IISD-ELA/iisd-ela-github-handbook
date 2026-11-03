# IISD-ELA GitHub Handbook

This repository contains the source files for the **IISD-ELA GitHub Handbook**, an online guide for IISD Experimental Lakes Area staff.

**[View the published handbook](https://iisd-ela.github.io/iisd-ela-github-handbook/)**

## Contents

1. **[Purpose](#purpose)**
2. **[Repository Structure and Files](#repository-structure-and-files)**
3. **[Contact](#contact)**

## Purpose

This handbook provides IISD-ELA staff with practical guidance on using our [GitHub organization](https://github.com/IISD-ELA) to preserve, organize, share, and collaborate on projects.

It documents organizational guidelines, the automated repository submission process, and step-by-step tutorials for GitHub workflows, from basic browser-based tasks to more advanced development practices.

The handbook is intended for staff of all experience levels, including those with no prior GitHub experience.

## Repository Structure and Files

The handbook is built using [mdBook](https://rust-lang.github.io/mdBook/), which converts Markdown files into a navigable website.

```text
iisd-ela-github-handbook/
├── .github/                              # GitHub configuration
│   └── workflows/                        # Automated workflows
│       └── deploy.yml                    # GitHub Pages deployment
├── src/                                  # Handbook content
│   ├── README.md                         # Handbook homepage
│   ├── SUMMARY.md                        # Navigation and chapter order
│   ├── why-use-github-at-iisd-ela.md     # Benefits of GitHub
│   ├── what-belongs-on-github.md         # Project and file guidelines
│   ├── getting-started.md                # Initial setup instructions
│   ├── github-learning-resources/        # GitHub tutorials
│   │   ├── introduction.md               # Learning resources overview
│   │   ├── level-1.md                    # Level 1 introduction
│   │   ├── level1/                       # Beginner tutorials
│   │   ├── level2/                       # Intermediate tutorials
│   │   └── level3/                       # Advanced tutorials
│   ├── appendices/                       # Reference materials
│   └── media/                            # Images and screenshots
├── theme/                                # Custom website styling
│   └── custom.css                        # Custom CSS
├── book.toml                             # mdBook configuration
├── .gitignore                            # Git exclusions
└── README.md                             # Repository documentation
```

**Key files and directories:**

- `src/` - Markdown chapters and supporting content.
- `src/SUMMARY.md` - Defines the handbook's navigation and chapter order.
- `src/media/` - Images and screenshots used throughout the handbook.
- `theme/` - Custom styling and other theme assets.
- `book.toml` - mdBook configuration.
- `.github/workflows/deploy.yml` - GitHub Actions workflow that automatically builds and deploys the handbook to GitHub Pages.
- `README.md` - This repository's documentation.

The generated `book/` directory is excluded from version control. The website is automatically rebuilt and published when changes are pushed to the `main` branch.

## Contact
For questions, suggestions, or corrections regarding this handbook, contact: iyaktubay@iisd-ela.org (Idil Yaktubay) or eladata@iisd-ela.org (IISD-ELA data team).
