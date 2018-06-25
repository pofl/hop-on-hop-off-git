

## The guide to learning Git

- The purpose of version control / source code management
    - [YouTube: What is Git](https://www.youtube.com/watch?v=OqmSzXDrJBk)
    - <https://en.wikipedia.org/wiki/Version_control>

### Basics of Git

#### Setting up a new repository

- `git init`

#### What are commits and how to commit

- Terminology: commits, index/stage, working directory
- Commits are identified by a unique hash which can be referred to with as little as its first six characters
- Commands: `status` / `add` / `commit`

#### What are branches and how to use them

- `diff`, `diff --cached` / `log`
- `branch` / `checkout` / `merge`

#### Beyond a local repo on your computer

- `clone`
- `push` / `fetch`
- (`remote`)

### Becoming proficient with Git

- [A Visual Git Reference](http://marklodato.github.io/visual-git-guide/index-en.html)

- References
    - Branches are refs
    - HEAD

- `rebase`  
  in addition to the VGR explanation, here are some links
    - [Getting solid at Git rebase vs. merge](https://medium.com/@porteneuve/getting-solid-at-git-rebase-vs-merge-4fa1a48c53aa)
    - [Git Interactive Rebase, Squash, Amend and Other Ways of Rewriting History](https://robots.thoughtbot.com/git-interactive-rebase-squash-amend-rewriting-history)

- `pull` / `pull --rebase` / `pull --ff-only`
    - (Stop using `pull`)
        - Use fetch
            - to understand that you're working with remote
            - to avoid merge commits
            - to consciously take appropriate actions
    - [When should I use `git pull --rebase`?](https://stackoverflow.com/questions/2472254/when-should-i-use-git-pull-rebase)

- Workflow
    - [Fork and Pull Request Workflow](https://github.com/susam/gitpr) (GitHub's ontribution workflow)
    - Getting a general idea of how to work with git: <https://sandofsky.com/blog/git-workflow.html> (but please respect our internal guidelines!)

- "Keep a clean Git history" they say
    - [How (and why!) to keep your Git commit history clean](https://about.gitlab.com/2018/06/07/keeping-git-commit-history-clean/)

- `git add --patch`

- Undoing things in Git
    - `reset` / `commit --amend`
    - <https://hackernoon.com/when-to-use-git-reset-git-revert-git-checkout-dc4824795d9>
    - <https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting>


- merge vs. fast-forward merge
    - <https://sandofsky.com/images/fast_forward.pdf>
    - Making a case against fast-forward merging

- `squash` / `commit --fixup` / `rebase --auto-squash`
    - <https://robots.thoughtbot.com/autosquashing-git-commits>

### Mastering Git. Beyond what you need to know.

- `HEAD~1`

- [Git Internals by Scott Chacon](https://github.com/pluralsight/git-internals-pdf) (how git works internally)

- Configuration
    - git log
        https://stackoverflow.com/questions/1057564/pretty-git-branch-graphs/35075021
    - Aliases
    - [How to keep git log and less output on the screen](http://serebrov.github.io/html/2014-01-04-git-log-and-less-keep-output.html)
    - tig
        - <https://www.atlassian.com/blog/git/git-tig>
    - difftool, mergetool
        - <https://developer.atlassian.com/blog/2015/12/tips-tools-to-solve-git-conflicts/>

- `reflog`

- `cherry-pick`

- <https://stackoverflow.com/questions/4044368/what-does-tree-ish-mean-in-git>