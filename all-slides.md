<!-- section 0 -->

# Git Workshop {#git-workshop .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

![the distributed version control system](assets/git.png){height="46px" width="110px"}

<!-- section 1 -->

# Git vs. GitHub {#git-vs.-github .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 2 -->

# Git vs. GitHub

  Git                                GitHub
  ---------------------------------- --------------------------------------
  Software                           Service
  command line tool                  GUI
  installed locally                  hosted on the web
  VCS to mange source code history   hosting service for GIT repositories

> GitHub uses Git as central tool for its service

<!-- section 3 -->

# Architecture {#architecture .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 4 -->

# Architecture - directed acyclic graph

> The history in Git is formed from the commit objects and creates a directed acyclic graph

![](assets/directed_acyclic_graph.png)

<!-- section 5 -->

# Architecture - 3-Tier-Architecture

![](assets/3tier.png){height="60%" width="60%"}

-   Files from staging area will move to Git Repository with commit
-   Useful if you do not want a commit for every added file, but e.g. want a changeset containing 5 added files

<!-- section 6 -->

# Architecture - Git-Workflow

![](assets/git-workflow.png){height="70%" width="70%"}

> Recommended sequence: commit → pull → push

<!-- section 7 -->

# Architecture - Distributed Development

![Each developer gets its own local repository](assets/distributed_dev.svg){height="60%" width="60%"}

-   Advantage: No network connection needed for commits.
-   Checkins in local repository also work if production branch in SVN is broken.

<!-- section 8 -->

# Architecture - Creating a new repository

> When you run `git init` in a folder, Git creates the `.git` directory

![](assets/file-tree.png)

> This `.git` directory contains your local repository data

![HEAD is a reference to the checked out commit](assets/git-folder.png)

<!-- section 9 -->

# Differences to TFS

> Git is recommended over TFS by Microsoft itself for new projects!

  --------------------------------------------------------------------------------
  TFS                                            Git
  ---------------------------------------------- ---------------------------------
  Centralised VCS                                Distributed VCS

  branches are folders in TFS folder hierarchy   private local branches possible
  --------------------------------------------------------------------------------

<!-- section 10 -->

# Migration form TFS to Git

-   history not needed: `git init` on current files
-   history is needed: http://git-tfs.com/
    -   `git tfs clone ...` instead of the usual `git clone ...`
    -   git-tfs works as two-way bridge so changes can also be pushed to TFS: `git tfs checkintool`

Plan your migration carefully:

-   usually large binary data is not put into Git -\> cleanup before migration
-   for big projects multiple Git-Repositories could be created and included via Submodule/Subtree

<!-- section 11 -->

# Git-Configuration

-   can be local for git-repository within `.git/config`
-   can be global via global flag `git config --global ...`
-   can be accessed via `git config --list`

Typical settings:

-   `git config --global core.editor "code --wait"`
-   `git config --global user.name "John Doe"`
-   `git config --global user.email johndoe@example.com`
-   `git config --global merge.tool kdiff3`
-   `git config --global credential.helper cache`

<!-- section 12 -->

# .gitignore

-   .gitinore-File specifies intentionally untracked files that Git should ignore
-   files alread track are not affected!
-   each line in .gitignore specifies a pattern

Pattern format:

-   `#` serves as a comment
-   `!` negates a pattern
-   `/` directory separator
    -   slash at beginning -\> relative to the .gitignore-directory, otherwise any level
    -   slash at end -\> matches only directories, otherwise also files
-   `*` matches anything except slash
-   `?` like `*` but only one character
-   `**` match in all directories, e.g. `**/foo`
-   `/**` matches everything inside, e.g. `foo/**`
-   `/**/` matches zero or more directories, e.g. `foo/**/foo`

<!-- section 13 -->

# Tooling

<!-- section 14 -->

# Tooling - IDEs

-   VisualStudio
-   VS-Code

<!-- section 15 -->

# Tooling - Other

-   Clients (Github Desktop, SourceTree, SmartGit, GitKraken, GitTower)
-   Explorer-Integration (TortoiseGit)
-   Merge-Tools (meld)
-   ZSH-Plugin
-   Azure Devops (mit Git)
-   Azure-Devops-Pipeline -\> Github-Action Converter

<!-- section 16 -->

# Branching

-   list branches with `git branch` or `git branch -v`
    -   with `--merged` or `--no-merged` option you can filter branches that you have/not merged into the branch you are currently on
-   Creating a new branch: `git branch <branchname>`
-   to rename a branch use `git branch --move bad-branch-name corrected-branch-name`
    -   push it with `git push --set-upstream origin corrected-branch-name`
    -   delete bad branch on remote with `git push origin --delete bad-branch-name`

<!-- section 17 -->

# Branching

![new branch "testing" created](assets/branch1.png)

<!-- section 18 -->

# Branching

![added commit to branch "testing"](assets/branch2.png)

<!-- section 19 -->

# Branching

![switched back to branch "master"](assets/branch3.png)

https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows

<!-- section 20 -->

# Branching Strategies {#branching-strategies .light-on-dark rx="1" bgcss="sea-gradient"}

-   GitFlow

-   GithubFlow

-   Trunk-Based Development

<!-- section 21 -->

# Branching Strategies: GitFlow

![](assets/gitflow.webp)

<!-- section 22 -->

# Branching Strategies: GitFlow

**Pros**

-   isolated features
-   code in master remains clean and organized. Only updated with tested code
-   easy traceability as merges are bundled/labeled
-   good for traditional software distribution

**Cons**

-   Many branches with complicated rules
-   Heavy maintenance workload for released versions
-   structured and specific development path conflict with agile iterative approach

<!-- section 23 -->

# Branching Strategies: Github-Flow

![](assets/githubflow.webp)

<!-- section 24 -->

# Branching Strategies: GithubFlow

**Pros**

-   clear and simple collaboration rules
-   Continuous integration and deployment
-   Less risk of technical debt with this branching strategy

**Cons**

-   Speed comes at cost of less organized workflow in comparison to Git-Flow
-   This branching stratey emphasizes constant deployment. Limitation for teams that tent to make larger releases or test several features together
-   release preparation and bug fixes happen both in master branch -\> requires attention

<!-- section 25 -->

# Branching Strategies: Trunk-Based-Development

![](assets/trunk-based-development.jpg)

<!-- section 26 -->

# Working with Git {#working-with-git .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 27 -->

# Working with Remotes

> "Remote repositories are versions of your project that are hosted on the Internet or network somewhere"

-   to list the current remotes you can use `git remote -v`
-   a remote can be inspected with `git remote show origin`
-   when cloning a repo the origin is already set to the repo you cloned from
-   remotes can be added with `git remote add pb <e.g. some github-repo-url>`
-   to remove a remote use `git remote remove <remote-name>`
-   fetching from a remote: `git fetch`
-   pulling from a remote: `git pull` (pull is a combination of `git fetch` and `git merge`)
-   pushing to a remote: `git push origin master`

<!-- section 28 -->

# Pull-Request

https://git-scm.com/docs/git-request-pull
https://www.atlassian.com/de/git/tutorials/making-a-pull-request

<!-- section 29 -->

# Git log

https://www.atlassian.com/git/tutorials/git-log

``` {.bash}
git log --decorate --graph --oneline --all
```

<!-- section 30 -->

# Tagging

-   list your existing tags with `git tag` or search with `git tag -l "v1.8.5*"`
-   you can create a tag with `git tag -a v1.9 -m "my version 1.9"`
-   to get the data of a tagged commit use `git show v1.9`
-   when tagging without -a, -m, -s option a lightweight tag is created only containing the commit checksum, e.g. `git tag v1.9-lw`
-   tagging later can be done by specifying the commit the should be tagged, e.g. `git tag -a v1.9 9fceb02`
-   by default `git push` does **not** transfer tags to the remote server, instead use `git push origin v1.9` or `git push origin --tags`
-   tags can be deleted by `git tag -d v1.9`
-   to checkout a tagged commit use `git checkout v1.9` (be aware of detached HEAD. Details: https://git-scm.com/book/en/v2/Git-Basics-Tagging)

<!-- section 31 -->

# Git Aliases

> can simplify your Git-experience by settig custom aliases that are easier/shorter to remember

e.g. `git config --global alias.unstage 'reset HEAD --'` enables usage of `git unstage fileA` instead of `git reset HEAD -- fileA`

<!-- section 32 -->

# Submodules

> A git submodule is a record within a host git repository that points to a specific commit in another external repository

-   Submodules do not track git refs or branches and are not automatically updated when the host repository is updated
-   If you need to maintain a strict version management over your external dependencies, it can make sense to use git submodules
-   When an external component or subproject is changing too fast or upcoming changes will break the API, you can lock the code to a specific commit for your own safety
-   if code in the submodule-repo gets updated you have to take care to update your submodule-reference to the latest version

`git submodule add https://bitbucket.org/somerepo/awesomelibrary`

<!-- section 33 -->

# Subtrees

> Lets you nest one repository into anothers as sub-directory

![](assets/BeforeAfterGitSubtreeDiagram.png)

**Pros**

-   The sub-project's code is available right after the clone of the super project is done
-   less overhead than Submodules (e.g. does not add new metadata files)

**Cons**

-   you have to learn a new merging strategy (subtree merge)
-   Contributing code back upstream for the sub-projects is slightly more complicated

<!-- section 34 -->

# Merge strategies

https://www.geeksforgeeks.org/merge-strategies-in-git/

> If not specified explicitly Git will automatically choose a strategy based on the branches provided for merging

-   **Fast Forward (Rebase)**
-   **Recursive**
-   Ours
-   Octopus
-   Resolve
-   Subtree

<!-- section 35 -->

# Merge: Fast Forward (Rebase)

![](assets/Fast-Forward-Merge.png)

<!-- section 36 -->

# Merge: Recursive

![](assets/Recursive-Merge.png)

<!-- section 37 -->

# Merge: Ours

![](assets/Ours-Merge.png)

<!-- section 38 -->

# Merge: Octopus

`git merge -s octopus`

![](assets/Octopus-Merge-Strategy.png)

> Resolves cases with more than two heads. It is primarily used for bundling topic branch heads together

> Linus Torvalds was not happy about a pull-request containing an octopus merge of 66 branches: https://marc.info/?l=linux-kernel&m=139033182525831

<!-- section 39 -->

# Merge: Resolve

`git merge -s resolve`

> Resolve two heads by using a 3-way-merge. Complex conflicts have to be solved manually.

![](assets/Resolve-Merge-Strategy.png)

<!-- section 40 -->

# Merge: Subtree

`git merge -s subtree`

![](assets/Subtree-Merge-Strategy.png)

> The idea of the subtree merge is that you have two projects, and one of the projects maps to a subdirectory of the other one.
> When you specify a subtree merge, Git is often smart enough to figure out that one is a subtree of the other and merge appropriately

<!-- section 41 -->

# Mergetool & Difftool

-   `git mergetool` opens the merge tool defined in git-config (e.g. meld)
-   `git diff Commit1sha Commit2sha` opens the diff tool defined in git-config

<!-- section 42 -->

# Merging vs. Rebasing vs. Cherry-Picking {#merging-vs.-rebasing-vs.-cherry-picking .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 43 -->

# Cherry-Picking

> Cherry picking can cause duplicate commits -\> often merges are better

Use cases for Cherry-Picking:

-   Team Collaboration, e.g. backend create data-structure and frontend-dev cherry-picks it
-   Bug-Fixing: hotfix can be cherry-picked to main branch before it affects more users

Usage: `git cherry-pick commitSha`

https://www.atlassian.com/de/git/tutorials/merging-vs-rebasing
https://git-scm.com/book/en/v2/Git-Branching-Rebasing
https://git-scm.com/book/en/v2/Distributed-Git-Maintaining-a-Project
https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Patching

<!-- section 44 -->

# Undoing commits

https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified

From local repository:

-   keeping your local changes: `git reset --soft HEAD`
-   discarding your local changes: `git reset --hard HEAD`
-   unstage staged file: `git restore --staged <filename>`
-   unmodifying a file: `git restore <filename>`

From public repository:

-   `git revert HEAD` and `git commit -m "reverted last commit"`

> HEAD points to last commit in branch: `git reset HEAD~<no-of-commits>`

If you want to add e.g. additional files to your previous commit you can use `git commit --amend` instead of creating an additional changeset

![](assets/Subtree-Merge-Strategy.png)

<!-- section 45 -->

# Git Replace

https://git-scm.com/book/en/v2/Git-Tools-Replace

<!-- section 46 -->

# Signing Commits/Tags

https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work

<!-- section 47 -->

# Rewriting History

https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

<!-- section 48 -->

# Staging

https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging

<!-- section 49 -->

# Stashing

https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning

<!-- section 50 -->

# Squashing

<!-- section 51 -->

# Submodules

https://git-scm.com/book/en/v2/Git-Tools-Submodules

<!-- section 52 -->

# Debugging with Git

-   File annotations: `git blame -L 3,5 <somefilename>`
-   git bisect:
    -   start with `git bisect start`
    -   use `git bisect bad` to tell the system that current commit is broken
    -   use `git bisect good <good_commit>` when the last known good state was
    -   goes to middle of possibly broken commits -\> check -\> git bisect bad/good
    -   when finished use `git bisect reset`
-   git grep can help you strings/regex in your files, e.g. `git grep -n <search-text>`

<!-- section 53 -->

# Git-Hooks

https://www.atlassian.com/git/tutorials/git-hooks
https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks

Enforcing Policies:

https://git-scm.com/book/en/v2/Customizing-Git-An-Example-Git-Enforced-Policy

Husky.NET

<!-- section 54 -->

# Handling large repositories

https://www.atlassian.com/git/tutorials/big-repositories
https://www.atlassian.com/git/tutorials/git-lfs

<!-- section 55 -->

# git gc && git prune

https://www.atlassian.com/git/tutorials/git-prune
https://www.atlassian.com/git/tutorials/git-gc

<!-- section 56 -->

# Best practices {#best-practices .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 57 -->

# Best practices

-   commit often: Each commit is a snapshot that can be reverted to. Commits can be combined using `rebase`.
-   work from latest version with `git pull` to avoid merge conflicts
-   commit notes should contain "why" and "what" of change
-   review changes before commiting
-   Use Branches: Enables developers to work in parallel on separate lines of product
-   Agree on a common workflow, e.g. Git-Flow -\> otherwise overhead in merges

<!-- section 58 -->

# Advanced stuff {#advanced-stuff .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 59 -->

# Advanced stuff

https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Basic-Snapshotting
https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection
https://git-scm.com/book/en/v2/Git-Tools-Rerere
https://git-scm.com/book/en/v2/Git-Tools-Bundling
https://git-scm.com/book/en/v2/Customizing-Git-Git-Attributes

-   Deletion von Elementen -\> Teasern

<!-- section 60 -->

# GitOps {#gitops .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 61 -->

# GitOps - What is GitOps?

> GitOps is code-based infrastructure and operational procedures that rely on Git as a source control system

> GitOps ensures that a cloud infrastructure is immediately reproducible based on the state of a Git repository.
> Pull requests modify the state of the Git repository.
> Once approved and merged, the pull requests will automatically reconfigure and sync the live infrastructure to the state of the repository.
> This live syncing pull request workflow is the core essence of GitOps

<!-- section 62 -->

# GitOps - Pipeline

To achieve a full GitOps install, a pipeline platform is required, e.g.:

-   Azure-Devops-Pipelines
-   Github-Actions
-   Gitlab Pipelines
-   Bitbucket Pipelines
-   Jenkins/Jenkins X
-   ArgoCD
-   Flux
-   Tekton Pipelines

<!-- section 63 -->

# GitOps - Example Pipeline

![](assets/gitops_cd_pipeline.png)

<!-- section 64 -->

# Ressources

-   Cheatsheet: https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet
-   Githug
-   learngitbranching.js.org
