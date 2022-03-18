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

# Architecture - Git-Workflow

![](assets/git-workflow.png){height="45%" width="45%"}

Recommended sequence: commit → pull → push

<!-- section 6 -->

# Architecture - Distributed Development

![](assets/distributed_dev.svg){height="50%" width="50%"}

<!-- section 7 -->

# Architecture - Distributed Development

-   Each developer has its own full repository

-   Advantage: No network connection needed for commits.

-   Checkins in local repository also work if production branch in SVN is broken.

<!-- section 8 -->

# Architecture - Creating a new repository

> When you run **`git init`** Git creates the **`.git`** directory which contains your local repository data

![](assets/file-tree.png)

![HEAD is a reference to the checked out commit](assets/git-folder.png)

<!-- section 9 -->

# GIT/TFS {#gittfs .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 10 -->

# Differences to TFS

  --------------------------------------------------------------------------------
  TFS                                            Git
  ---------------------------------------------- ---------------------------------
  Centralised VCS                                Distributed VCS

  branches are folders in TFS folder hierarchy   private local branches possible
  --------------------------------------------------------------------------------

> Git is recommended over TFS by Microsoft itself for new projects!

<!-- section 11 -->

# Migration form TFS to Git

-   history not needed: **`git init`** on current files

-   history is needed: http://git-tfs.com/

    -   **`git tfs clone ...`** instead of the usual **`git clone ...`**
    -   git-tfs works as two-way bridge so changes can also be pushed to TFS: **`git tfs checkintool`**

<!-- section 12 -->

# Migration form TFS to Git

Plan your migration carefully:

-   cleanup before migration: e.g. large file → NuGet-Packages

-   for big projects multiple Git-Repositories could be created and included via Submodule/Subtree

<!-- section 13 -->

# Git-Configuration

-   can be local for git-repository within **`.git/config`**

-   can be global via global flag **`git config --global ...`**

-   can be accessed via **`git config --list`**

<!-- section 14 -->

# Git-Configuration

Typical settings:

-   `git config --global core.editor "code --wait"`
-   `git config --global user.name "John Doe"`
-   `git config --global user.email johndoe@example.com`
-   `git config --global merge.tool kdiff3`
-   `git config --global credential.helper cache`

<!-- section 15 -->

# .gitignore

-   .gitinore-File specifies files that Git should ignore

-   files already track are not affected!

-   each line in .gitignore specifies a pattern

<!-- section 16 -->

# .gitignore - Patterns

-   **`#`** serves as a comment
-   **`!`** negates a pattern
-   **`/`** directory separator
    -   slash at beginning → relative to the .gitignore-directory, otherwise any level
    -   slash at end → matches only directories, otherwise also files
-   **`*`** matches anything except slash
-   **`?`** like **`*`** but only one character
-   **`**`** match in all directories, e.g. **`**/foo`**
-   **`/**`** matches everything inside, e.g. **`foo/**`**
-   **`/**/`** matches zero or more directories, e.g. **`foo/**/foo`**

<!-- section 17 -->

# Tooling {#tooling .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 18 -->

# Tooling

-   IDEs: VisualStudio, VS-Code
-   Clients: Github Desktop, SourceTree, SmartGit, GitKraken, GitTower
-   Explorer-Integration: TortoiseGit
-   Merge-Tools: meld, kdiff3
-   Shells: ZSH+Plugin
-   Azure-Devops-Pipeline → Github-Action Converter
-   Git LFS

<!-- section 19 -->

# Branching {#branching .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 20 -->

# Branching

Creating a new branch: **`git branch <branchname>`**

> branches are very lightweight in Git: You can have many and switch very fast.

<!-- section 21 -->

# Branching

list branches with **`git branch`** or **`git branch -v`**

with **`--merged`** or **`--no-merged`** option you can filter branches that you have/not merged into the branch you are currently on

<!-- section 22 -->

# Branching

-   rename branch with **`git branch --move bad-branch-name corrected-branch-name`**
    -   push it with **`git push --set-upstream origin corrected-branch-name`**
    -   delete bad branch on remote with **`git push origin --delete bad-branch-name`**

<!-- section 23 -->

# Branching

![new branch "testing" created](assets/branch1.png)

<!-- section 24 -->

# Branching

![added commit to branch "testing"](assets/branch2.png)

<!-- section 25 -->

# Branching

![switched back to branch "master"](assets/branch3.png)

<!-- section 26 -->

# Branching Strategies {#branching-strategies .light-on-dark rx="1" bgcss="sea-gradient"}

-   GitFlow

-   GithubFlow

-   GitlabFlow

-   Trunk-Based Development

<!-- section 27 -->

# GitFlow

![](assets/gitflow.webp)

<!-- section 28 -->

# GitFlow

**Pros**

-   isolated features
-   Only tested code comes in master
-   easy traceability as merges are bundled/labeled
-   good for traditional software distribution

**Cons**

-   Many branches with complicated rules
-   Heavy maintenance workload for released versions
-   structured and specific development path conflicts with agile iterative approach

<!-- section 29 -->

# Github-Flow

![](assets/githubflow.webp)

<!-- section 30 -->

# GithubFlow

https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/
https://docs.github.com/en/get-started/quickstart/github-flow

**Pros**

-   clear and simple collaboration rules
-   Continuous integration and deployment
-   Less risk of technical debt with this branching strategy

**Cons**

-   Speed comes at cost of less organized workflow in comparison to Git-Flow
-   This branching stratey emphasizes constant deployment. Limitation for teams that tent to make larger releases or test several features together
-   release preparation and bug fixes happen both in master branch → requires attention

<!-- section 31 -->

# GitlabFlow

<!-- section 32 -->

# Trunk-Based-Development

![](assets/trunk-based-development.jpg)

https://www.atlassian.com/de/continuous-delivery/continuous-integration/trunk-based-development
https://trunkbaseddevelopment.com/

<!-- section 33 -->

# Trunk-Based-Development

Trunk-Based-Development is recommended in this book

![](assets/accelerate.jpg)

<!-- section 34 -->

# Comparison of Workflows

https://www.atlassian.com/de/git/tutorials/comparing-workflows/gitflow-workflow
https://www.flagship.io/git-branching-strategies/
https://reviewpad.com/blog/github-flow-trunk-based-development-and-code-reviews/

<!-- section 35 -->

# Working with Git {#working-with-git .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 36 -->

# Working with Remotes

> "Remote repositories are versions of your project hosted on Internet or network somewhere"

<!-- section 37 -->

# Working with Remotes

-   to list the current remotes you can use **`git remote -v`**
-   a remote can be inspected with **`git remote show origin`**
-   when cloning a repo the origin is already set to the repo you cloned from
-   remotes can be added with **`git remote add pb <e.g. some github-repo-url>`**
-   to remove a remote use **`git remote remove <remote-name>`**
-   fetching from a remote: **`git fetch`**
-   pulling from a remote: **`git pull`** (pull is a combination of **`git fetch`** and **`git merge`**)
-   pushing to a remote: **`git push origin master`**

<!-- section 38 -->

# Pull-Request

> "Generate a request asking your upstream project to pull changes into their tree."

Push: **`git push https://git.ko.xz/project master`**

vs.

Pull-Request: **`git request-pull v1.0 https://git.ko.xz/project master`**

<!-- section 39 -->

# Git log

Showing the history:

-   all: **`git log --decorate --graph --oneline --all`**
-   by amount: **`git log -3`**
-   by date: **`git log --after="2014-7-1"`**
-   by author: **`git log --author="John"`**
-   by message: **`git log --grep="JRA-224:"`**
-   by file: **`git log -- foo.py bar.py`**
-   by content: **`git log -S"Hello, World!"`**
-   by range: **`git log main..feature`**
-   by merges: **`git log --merges`** or **`git log --no-merges`**

<!-- section 40 -->

# Tagging

-   you can create a tag with `git tag -a v1.9 -m "my version 1.9"`
-   list your existing tags with `git tag` or `git tag -l "v1.8.5*"`
-   to get the data of a tagged commit use: `git show v1.9`
-   without -a, -m, -s option a lightweight tag containing only checksum is created:`git tag v1.9-lw`
-   tagging later can be done by specifying the commit the should be tagged: `git tag -a v1.9 9fceb02`
-   by default `git push` does **not** transfer tags. instead use `git push origin v1.9` or `git push origin --tags`
-   tags can be deleted with `git tag -d v1.9`
-   to checkout a tagged commit use `git checkout v1.9` (be aware of detached HEAD. Details: https://www.git-tower.com/learn/git/faq/detached-head-when-checkout-commit)

<!-- section 41 -->

# Git Aliases

> "Can simplify your Git-experience by settig custom aliases that are easier/shorter"

**`git config --global alias.unstage 'reset HEAD --'`**

→ **`git unstage fileA`** instead of **`git reset HEAD -- fileA`**

<!-- section 42 -->

# Submodules

> A git submodule is a record within a host git repository that points to a specific commit in another external repository

`git submodule add https://bitbucket.org/somerepo/awesomelibrary`

<!-- section 43 -->

# Submodules

-   Submodules do not track git refs or branches and are not automatically updated when the host repository is updated
-   If you need to maintain a strict version management over your external dependencies, it can make sense to use git submodules

<!-- section 44 -->

# Subtrees

![nests one repository into anothers as sub-dir](assets/BeforeAfterGitSubtreeDiagram.png){height="80%" width="80%"}

<!-- section 45 -->

# Subtrees

**Pros**

-   The sub-project's code is available right after the clone of the super project is done
-   less overhead than Submodules (e.g. does not add new metadata files)

**Cons**

-   you have to learn a new merging strategy (subtree merge)
-   contributing code back to the sub-projects is more complicated

<!-- section 46 -->

# Merge strategies

> If not specified explicitly Git will automatically choose a strategy based on the branches provided for merging

-   **Fast Forward**
-   **Recursive**
-   Ours
-   Octopus
-   Resolve
-   Subtree

<!-- section 47 -->

# Merge: Fast Forward (Rebase)

![](assets/Fast-Forward-Merge.png)

-   most commonly used merge strategy. history is just one straight line.
-   No new merges on the master between branch creation and merge to master.

<!-- section 48 -->

# Merge: Recursive

![](assets/Recursive-Merge.png)

-   New commits on master before branch is merged back to master

<!-- section 49 -->

# Merge: Ours

![](assets/Ours-Merge.png)

-   resolves any number of heads → resulting tree of merge is that of the current branch head ignoring all changes from other branches

<!-- section 50 -->

# Merge: Octopus

`git merge -s octopus`

![](assets/Octopus-Merge-Strategy.png)

-   Resolves cases with more than two heads. It is primarily used for bundling topic branch heads together
-   Linus Torvalds was not happy about a pull-request containing an octopus merge of 66 branches: https://marc.info/?l=linux-kernel&m=139033182525831

<!-- section 51 -->

# Merge: Resolve

`git merge -s resolve`

-   Resolve two heads by using a 3-way-merge. Complex conflicts have to be solved manually.

![](assets/Resolve-Merge-Strategy.png)

<!-- section 52 -->

# Merge: Subtree

`git merge -s subtree`

![](assets/Subtree-Merge-Strategy.png)

-   Git is often smart enough to figure out that one is a subtree of the other and merge appropriately

<!-- section 53 -->

# Mergetool & Difftool

-   `git mergetool` opens the merge tool defined in git-config (e.g. meld)
-   `git diff Commit1sha Commit2sha` opens the diff tool defined in git-config

<!-- section 54 -->

# Merging vs. Rebasing vs. Cherry-Picking {#merging-vs.-rebasing-vs.-cherry-picking .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 55 -->

# Cherry-Picking

> Cherry picking can cause duplicate commits → often merges are better

Usage: `git cherry-pick commitSha`

<!-- section 56 -->

# Cherry-Picking

Use cases for Cherry-Picking:

-   Team Collaboration, e.g. backend create data-structure and frontend-dev cherry-picks it
-   Bug-Fixing: hotfix can be cherry-picked to main branch before it affects more users

https://www.atlassian.com/de/git/tutorials/merging-vs-rebasing
https://git-scm.com/book/en/v2/Git-Branching-Rebasing
https://git-scm.com/book/en/v2/Distributed-Git-Maintaining-a-Project
https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Patching

<!-- section 57 -->

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

<!-- section 58 -->

# Git Replace

https://git-scm.com/book/en/v2/Git-Tools-Replace

<!-- section 59 -->

# Signing Commits/Tags

https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work

<!-- section 60 -->

# Rewriting History

https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

<!-- section 61 -->

# Staging

https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging

<!-- section 62 -->

# Stashing

https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning

<!-- section 63 -->

# Squashing

<!-- section 64 -->

# Submodules

https://git-scm.com/book/en/v2/Git-Tools-Submodules

<!-- section 65 -->

# Debugging with Git

-   File annotations: `git blame -L 3,5 <somefilename>`
-   git bisect:
    -   start with `git bisect start`
    -   use `git bisect bad` to tell the system that current commit is broken
    -   use `git bisect good <good_commit>` when the last known good state was
    -   goes to middle of possibly broken commits → check → git bisect bad/good
    -   when finished use `git bisect reset`
-   git grep can help you strings/regex in your files, e.g. `git grep -n <search-text>`

<!-- section 66 -->

# Git-Hooks

https://www.atlassian.com/git/tutorials/git-hooks
https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks

Enforcing Policies:

https://git-scm.com/book/en/v2/Customizing-Git-An-Example-Git-Enforced-Policy

Husky.NET

<!-- section 67 -->

# Handling large repositories

https://www.atlassian.com/git/tutorials/big-repositories
https://www.atlassian.com/git/tutorials/git-lfs

<!-- section 68 -->

# git gc && git prune

https://www.atlassian.com/git/tutorials/git-prune
https://www.atlassian.com/git/tutorials/git-gc

<!-- section 69 -->

# Best practices {#best-practices .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 70 -->

# Best practices

-   commit often: Each commit is a snapshot that can be reverted to. Commits can be combined using `rebase`.
-   work from latest version with `git pull` to avoid merge conflicts
-   commit notes should contain "why" and "what" of change
-   review changes before commiting
-   Use Branches: Enables developers to work in parallel on separate lines of product
-   Agree on a common workflow, e.g. Git-Flow → otherwise overhead in merges

<!-- section 71 -->

# Advanced stuff {#advanced-stuff .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 72 -->

# Advanced stuff

https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Basic-Snapshotting
https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection
https://git-scm.com/book/en/v2/Git-Tools-Rerere
https://git-scm.com/book/en/v2/Git-Tools-Bundling
https://git-scm.com/book/en/v2/Customizing-Git-Git-Attributes

-   Deletion von Elementen → Teasern

<!-- section 73 -->

# GitOps {#gitops .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 74 -->

# GitOps - What is GitOps?

> GitOps is code-based infrastructure and operational procedures that rely on Git as a source control system

> GitOps ensures that a cloud infrastructure is immediately reproducible based on the state of a Git repository.
> Pull requests modify the state of the Git repository.
> Once approved and merged, the pull requests will automatically reconfigure and sync the live infrastructure to the state of the repository.
> This live syncing pull request workflow is the core essence of GitOps

<!-- section 75 -->

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

<!-- section 76 -->

# GitOps - Example Pipeline

![](assets/gitops_cd_pipeline.png)

<!-- section 77 -->

# Ressources

-   https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet
-   https://github.com/Gazler/githug
-   https://learngitbranching.js.org
-   https://docs.microsoft.com/de-de/learn/paths/intro-to-vc-git/
