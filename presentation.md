name: default
layout: true
class: center, middle
---
name: inverse
layout: true
class: center, middle, inverse
---
template: default
# Version Control
### For software project the source code is like the crown jewels, a precious asset that must be protected. We accomplish this with a version control, a special set of software tools that keep track of every modification. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members.
### If you're a developer who has never used version control you may have added versions to your files, perhaps with suffixes like "final" or "latest" and then had to later deal with a new final version. Perhaps you've commented out code blocks because you want to disable certain functionality without deleting the code, fearing that there may be a use for it later. Version control is a way out of these problems.
---
layout: false
.left-column[
  ## Benefits of version control
]
.right-column[
- Developing software without version control is like not having any backups. It allows software teams to maintain efficiency and agility as the team scales to include more developers

- A long term history of every file. This includes every change made by many individuals. These changes include creation, deletion and modification. Having a complete history allows us to go back in time to help developers analyse bugs and mistakes.

- Branching and merging allows team members to work concurrently. Creating a branch keeps multiple streams of work independent of each other until it ready to go into production. Providing the ability to review the work that has been done and developers can verify the integrity of the changes made

- Traceability. Being able to trace each change made to the software with a message describing the intent of the change, helps with analysis when trying to find a problem
]
---
layout: false
.left-column[
  ## Benefits of version control
  ## Version control software
]
.right-column[
- There are many types of version control software and different approaches. You get client server models and disturbed models

- Distributed vs. Centralized approach. Rather than having a single, central repository on which clients synchronize, each peer's working copy of the codebase is a complete repository

- SVN is an example of client server model

- Some distributed software examples: Git, Mercurial, Visual Studio Team Services

- By far, the most widely used modern version control system in the world today is Git. Git is a mature, actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel.
]

---
layout: false
.left-column[
  ## Benefits of version control
  ## Version control software
  ## Version control with Git
]
.right-column[

- Git is the best choice for most software teams today. Here are the main reasons why version control with Git is preferred over alternatives:

- Git is a de facto standard: Git is the most broadly adopted tool of its kind. While some organizations may need to climb the learning curve when migrating to Git from another version control system, many of their existing and future developers do not need to be trained on Git

- Git is a quality open source project: Git enjoys great community support and a vast user base. Documentation is excellent and plentiful, including books, tutorials and dedicated web sites. Being open source it lowers the cost for hobbyist developers as they can use Git without paying a fee.

- Git has great performance, security and flexability

- Although Git has a difficult learning curve. Especially for those teams coming from a non-distributed VCS, having a central repository may seem like a good thing that they don't want to lose. However you can still have an official, canonical repository where all changes to the software must be store.
]

---
layout: false
.left-column[
  ## Benefits of version control
  ## Version control software
  ## Version control with Git
  ## How to use git
]
.right-column[
  [A simple Git guide](http://rogerdudler.github.io/git-guide/)
]

---
layout: false
.left-column[
  ## Benefits of version control
  ## Version control software
  ## Version control with Git
  ## How to use git
  ## Workflows
]
.right-column[
- ## Centralized Workflow
  Like Subversion, the Centralized Workflow uses a central repository to serve as the single point-of-entry for all changes to the project. Instead of trunk, the default development branch is called master and all changes are committed into this branch. This workflow doesn’t require any other branches besides master.
- ## Feature Workflow
  The core idea behind the Feature Branch Workflow is that all feature development should take place in a dedicated branch instead of the master branch. This encapsulation makes it easy for multiple developers to work on a particular feature without disturbing the main codebase. It also means the master branch will never contain broken code, which is a huge advantage for continuous integration environments.
]
---
layout: false
.left-column[
  ## Benefits of version control
  ## Version control software
  ## Version control with Git
  ## How to use git
  ## Workflows
]
.right-column[
- ## Gitflow Workflow
  The Gitflow Workflow defines a strict branching model designed around the project release. While somewhat more complicated than the Feature Branch Workflow, this provides a robust framework for managing larger projects.

  This workflow doesn’t add any new concepts or commands beyond what’s required for the Feature Branch Workflow.

  Instead, it assigns very specific roles to different branches and defines how and when they should interact.

  In addition to feature branches, it uses individual branches for preparing, maintaining, and recording releases. Of course, you also get to leverage all the benefits of the Feature Branch Workflow: pull requests, isolated experiments, and more efficient collaboration.
]
---
layout: false
.left-column[
  ## Gitflow - How it works
]
.right-column[
- The Gitflow Workflow still uses a central repository as the communication hub for all developers

- Developers work locally and push branches to the central repo

- The only difference is the branch structure of the project.

- Historical Branches, Feature Branches, Release Branches, Maintenance Branches
]
---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches
]
.right-column[
- Instead of a single `master` branch, this workflow uses two branches to record the history of the project. The `master` branch stores the official release history, and the `develop` branch serves as an integration branch for features. It's also convenient to tag all commits in the `master` branch with a version number.


![](02.svg)


- The rest of this workflow revolves around the distinction between these two branches.
]
---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

]
.right-column[
- Each new `feature` should reside in its own branch. But, instead of branching off of `master`, `feature` branches use `develop` as their parent branch.
- When a `feature` is complete, it gets merged back into `develop`. Features should never interact directly with `master`.


![](03.svg)


- Note that `feature` branches combined with the `develop` branch is, for all intents and purposes, the Feature Branch Workflow. But, the Gitflow Workflow doesn’t stop there.
]

---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

  - Release Branches
]
.right-column[
![](04.svg)

- Once `develop` has acquired enough features for a release (or a predetermined release date is approaching), you fork a `release` branch off of `develop`.

- Creating this branch starts the next release cycle, so no **new features** can be added after this point—only bug fixes, documentation generation, and other release-oriented tasks should go in this branch.

]

---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

  - Release Branches
]
.right-column[
![](04.svg)

- Once it's ready to ship, the release gets merged into `master` and tagged with a version number. In addition, it should be merged back into `develop`, which may have progressed since the release was initiated.

- Using a dedicated branch to prepare releases makes it possible for one team to polish the current release while another team continues working on features for the next release. It also creates well-defined phases of development (e.g., it's easy to say, “this week we're preparing for version 4.0” and to actually see it in the structure of the repository).
]

---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

  - Release Branches
]
.right-column[
![](04.svg)

##Common conventions
- branch off: `develop`
- merge into: `master`
- naming convention: `release-*` or `release/*`
]

---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

  - Release Branches

  - Maintenance Branches
]
.right-column[
![](05.svg)

- Maintenance or “hotfix” branches are used to quickly patch production releases. This is the only branch that should fork directly off of `master`

- As soon as the fix is complete, it should be merged into both `master` and `develop` (or the current release branch), and `master` should be tagged with an updated version number.

]
---
layout: false
.left-column[
  ## Gitflow - How it works
  - Historical Branches

  - Feature Branches

  - Release Branches

  - Maintenance Branches
]
.right-column[
![](05.svg)

- Having a dedicated line of development for bug fixes lets your team address issues without interrupting the rest of the workflow or waiting for the next release cycle. You can think of maintenance branches as ad hoc release branches that work directly with `master`.

- [Example](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow)
]
---
template: none
# Resources
[Version Control](https://www.atlassian.com/git/tutorials/what-is-version-control) /
[Git](https://git-scm.com/) /
[Git Cheat Sheet](https://www.atlassian.com/dam/jcr:8132028b-024f-4b6b-953e-e68fcce0c5fa/atlassian-git-cheatsheet.pdf) /
[Git Flow](https://github.com/nvie/gitflow) /
[Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/) /
[Git Flow Cheat Sheet](https://danielkummer.github.io/git-flow-cheatsheet/)

## Desktop Clients
[Sourcetree](https://www.sourcetreeapp.com/) /
[Git Desktop](https://desktop.github.com/)
---
![](in-case-of-fire-1-git-commit-2-git-push-3-leave-building2.png)
