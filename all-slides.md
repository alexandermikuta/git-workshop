<!-- section 0 -->

# Git Workshop {#git-workshop .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

![the distributed version control system](assets/git.png){height="46px" width="110px"}

<!-- section 1 -->

# Architecture {#architecture .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 2 -->

# Architecture - directed acyclic graph

> The history in Git is formed from the commit objects and creates a directed acyclic graph

![](assets/directed_acyclic_graph.png)

<!-- section 3 -->

# Architecture - 3-Tier-Architecture

![](assets/3tier.png){height="60%" width="60%"}

> Files from staging area will move to Git Repository with commit
> Useful if you do not want a commit for every added file, but e.g. want a changeset containing 5 added files

<!-- section 4 -->

# Architecture - Git-Workflow

![](assets/git-workflow.png){height="80%" width="80%"}

> Recommended sequence: commit → pull → push

<!-- section 5 -->

# Architecture - Distributed Development

![Each developer gets its own local repository](assets/distributed_dev.svg){height="80%" width="80%"}

> Advantage: No network connection needed for commits.
> Checkins in local repository also work if production branch in SVN is broken.

<!-- section 6 -->

# Architecture - Git as Folder

> When you run `git init` in a folder, Git creates the `.git` directory containing your local git repository

<!-- section 7 -->

# Branching Strategies {#branching-strategies .light-on-dark rx="1" bgcss="sea-gradient"}

-   GitFlow

-   GithubFlow

-   Trunk-Based Development

<!-- section 8 -->

# Branching Strategies - GitFlow

## Pros

-   isolated features ensure you have no need to freeze development or master branch for release preparation

-   code in master remains clean and organized. Only updated with tested code

-   easy traceability as merges are bundled and clearly labeled

-   conductive to the distribution of traditional software

<!-- subsection 8 / 1 -->

## Cons

-   Many branches with complicated rules

-   Heavy maintenance workload for released versions

-   structured and specific development path conflict with agile iterative approach

![](assets/gitflow.webp)

<!-- section 9 -->

# Branching Strategies - GitFlow

## Pros

-   clear and simple collaboration rules

-   Continuous integration and deployment

-   Less risk of technical debt with this branching strategy

<!-- subsection 9 / 1 -->

## Cons

-   Speed comes at cost of less organized workflow in comparison to Git-Flow

-   This branching stratey emphasizes constant deployment. Limitation for teams that tent to make larger releases or test several features together

-   release preparation and bug fixes happen both in master branch -\> requires attention

<!-- section 10 -->

# Branching Strategies - Github-Flow

![](assets/githubflow.webp)

<!-- section 11 -->

# Branching Strategies - Trunk-Based-Development

![](assets/trunk-based-development.jpg)

<!-- section 12 -->

# Best practices {#best-practices .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 13 -->

# Best practices

-   commit often: Each commit is a snapshot that the codebase can be reverted to. A group of commits can be combined into a single commit using `rebase`

-   Ensure you are working from latest version with `git pull` before making updates to the code. This helps avoiding merge conflicts

-   Make detailed notes: Each commit has a correspondig log entry. These messages should contain "why" and "what" of the commit.

-   Review changes before commiting: The staging area can be used to collect a group of edits before commiting them. This can be used to manage and review changes.

-   Use Branches: Enable several developers to work in parallel on separate lines of the product

-   Agree on a common workflow, e.g. Git-Flow -\> otherwise overhead in merges

<!-- section 14 -->

# Tooling

<!-- section 15 -->

# Tooling - IDEs

-   VisualStudio
-   VS-Code

<!-- section 16 -->

# Tooling - Other

-   Clients (Github Desktop, SourceTree, SmartGit, GitKraken, GitTower)
-   Explorer-Integration (TortoiseGit)
-   Merge-Tools (meld)
-   ZSH-Plugin
-   Azure Devops (mit Git)
-   Unterschied Git/Github
-   Git-TFS-Plugin
-   Azure-Devops-Pipeline -\> Github-Action Converter

<!-- section 17 -->

# Important commands {#important-commands .light-on-dark bgcss="sea-gradient" x="0" y="0" rz="-.1"}

<!-- section 18 -->

# Important commands: showing the history

``` {.bash}
git log --decorate --graph --oneline --all
```

-   Commits/signierte Commits
-   Blobs
-   Referenzen
-   .gitignore
-   Merge/Octopus-Merge
-   Pull-Requests
-   Cherry-Picking
-   Reset
-   Rebasing
-   Revert
-   Staging
-   Stashing
-   Squashing
-   Deletion von Elementen -\> Teasern
-   Hooks (z.B. Linting)
-   Tags/signierte Tags
-   Submodules
-   Subtrees
-   Fehlersuche mit "git bisect"
-   Git-Alias
-   Git-LFS
-   Linting von Commits/Commit-Messages (z.B. mittels Husky.Net)

<!-- section 19 -->

# GitOps

-   Github-Actions (Azure-Devops-Pipelines)

<!-- section 20 -->

# Ressources

-   Githug
-   learngitbranching.js.org

<!-- section 21 -->

# cool looking {#cool-looking .light-on-dark bg="white;assets/paperclip.gif" rx="-1" ry="0"}

leverages battle-proven`</br>`{=html}HTML5 presentation frameworks:

revealjs • impressjs

<!-- section 22 -->

# asciiart (ditaa) {#asciiart-ditaa .ltr rx="0" ry="1"}

``` {.render_ditaa args="--transparent --scale 1 --font 'Raleway'"}
+-----------------------------+
| Node A                      |
|                             |
| +----------+   +----------+ |
| |          |   |          | |
| | Frontend |   | Foo      | |
| |          |   |          | |
| |          |   | {s}      | |
| +-----+----+   +----------+ |
|       ^                     |
|       |                     |
|       \-service-\           |
|                 |           |
+-----------------|-----------+
                  |
+-----------------|-----------+
| Node B          |           |
|       /---------/           |
|       |                     |
|       v                     |
| +-----+----+   +=---------+ |
| |          |   |          | |
| | Frontend |   | Bar      | |
| |          |   |          | |
| |          |   | {s}      | |
| +----------+   +----------+ |
+-----------------------------+
```

<!-- section 23 -->

# asciiart (a2s) {#asciiart-a2s .ltr}

``` {.render_a2s}
#--------------------.
|[0]                 |
| .---# .---# #---.  |
| |[1]| |[1]| |[1]|  |
| #---' #---' '---#  |
|   ^     ^     ^    |
#---+-----+-----+----#
|   |     |     |    |
|   a     2 sketch   |
'--------------------#

[0]: {"fill": "#933","a2s:delref":true}
[1]: {"fill": "#bbb","a2s:delref":true,"a2s:type":"storage"}
```

<!-- section 24 -->

# asciiart (sketchy) {#asciiart-sketchy .ltr}

``` {.render_a2sketch}
#-----------------------------#
|[0]                          |
| Node                        |
|                             |
| #----------#   #----------# |
| |          |   |[1]       | |
| |front     |   | foo      | |
| |          |   |          | |
| |  ^       |   |          | |
| |  |       |   |          | |
| #--|-------#   #----------# |
|    |                ^       |
|    |                |       |
|    '-- service    --'       |
|                             |
#-----------------------------#
[0]: {"fill":"#fff","fillStyle":"solid","a2s:delref":true}
[1]: {"fill":"#eee","fillStyle":"solid","a2s:delref":true}
```

<!-- section 25 -->

# asciiart (svgbob) {#asciiart-svgbob .ltr rx="-1" ry="0"}

``` {.render_svgbob args="--scale 10 --font-family Raleway --font-size 24"}
        P *
           \
            \
       v0    \       v3
         *----\-----*
        /      v X   \
       /        o     \
      /                \
  v1 *------------------* v2
```

<!-- section 26 -->

# asciiart (mermaid) {#asciiart-mermaid .ltr}

``` {.render_mermaid args="-w 400" style="font-size: 100%;"}
graph LR
   a --> b & c--> d
```

<!-- section 27 -->

# asciiart (plantuml) {#asciiart-plantuml .ltr}

``` {.render_plantuml args="-Sbackgroundcolor=transparent -SdefaultFontSize=24 -SdefaultFontName=Raleway"}
@startuml
Bob->Alice : hello
Alice->Bob : oh, you again...
Bob->Alice : ??
@enduml
```

<!-- section 28 -->

# asciiart (graphviz) {#asciiart-graphviz .ltr}

``` {.render_dot args="-Nfontname=Raleway"}
digraph G {
    bgcolor=transparent;
    node [style=filled,color=white];

    a -> b -> c;
    a -> c;
    b -> d;
}
```

<!-- section 29 -->

# charts (vega-lite) {#charts-vega-lite .ltr rx="0" ry="-1"}

``` {.render_vegalite}
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"a": "A","b": 28}, {"a": "B","b": 55}, {"a": "C","b": 43},
            {"a": "D","b": 91}, {"a": "E","b": 81}, {"a": "F","b": 53},
            {"a": "G","b": 19}, {"a": "H","b": 87}, {"a": "I","b": 52}
        ]
    },
    "width": 250,
    "height": 300,
    "mark": "area",
    "encoding": {
        "x": {"field": "a", "type": "ordinal"},
        "y": {"field": "b", "type": "quantitative", "scale": {"domain": [0, 100]}}
    },
    "config": {
        "axis": {
            "labelFont": "Raleway",
            "labelFontSize": 18,
            "titleFont": "Raleway",
            "titleFontSize": 24,
            "titleAngle": 0
        },
        "axisX": {
            "labelAngle": 0
        }
    }
}
```
