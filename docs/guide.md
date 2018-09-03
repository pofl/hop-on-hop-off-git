# Becoming proficient with Git

## [The Visual Git Reference (VGR)](http://marklodato.github.io/visual-git-guide/index-en.html)

- This is the mother of all informative resources about Git. Read it very carefully.

## A Git repository is a directed acyclic graph (DAG) of commits

- The commit DAG is frequently reported to be "the most important thing to realize about git". You should strive to _understand every git command in terms of how it manipulates the commit graph!_ The VGR is an excellent resource to understand this.
- Have a look at the DAG of your repository with `git log --all --decorate --oneline --graph` (log adog / _"look, a dog!"_)
- What you need to internalize is that __commits are nodes in a DAG__. All commits have one parent commit, merge commits have two parents.
- Another concept you need to understand are references. __Branches, tags and HEAD are all references__. Which basically means they are an alias of a particular commit.
- Examples: "`merge`creates a commit with two parent commits", "`cherry-pick` takes a list of commit hashes and applies them as patches onto HEAD" and "`reset` takes a reference to or the hash of a commit and makes the current branch point to it".
- [HEAD is a special reference](https://blog.thoughtram.io/git/rebase-book/2015/02/10/understanding-branches-in-git.html).
- [Relative references](https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git), like `HEAD~2` are very helpful too.

## Rebasing

- Rebasing is an alternative to merging in that both of them are ways to integrate two branches. A `rebase` is a special case of `cherry-pick`.

### `cherry-pick`

- Select commits by their hashes and apply them one-by-one onto HEAD
- See the VGR for visual aid.

### `rebase`

- Rebase does the same as cherry-pick, only for entire branches automatically. The VGR explains the technical side of rebases pretty well.
- This guide -- [Getting solid at Git rebase vs. merge](https://medium.com/@porteneuve/getting-solid-at-git-rebase-vs-merge-4fa1a48c53aa) -- explains in depth and in length the ins and outs of rebase in contrast with merge. It's very lengthy and also goes into many details that will be covered later in this guide. You should probably skip this and revisit it later.

### `push --force` / `push --force-with-lease`

- After you rebased a branch it contains different commits than before. Because of that `git push` will reject your changes.
- A full explanation of the problem and why `--force-with-lease` is a better solution than `--force` can be found [here](https://developer.atlassian.com/blog/2015/04/force-with-lease/).

## Working with remotes

- `git fetch --all`
    - [`git pull --all`](https://stackoverflow.com/questions/4318161/can-git-pull-all-update-all-my-local-branches) will not pull all branches
- `push --set-upstream`
- `git branch -vva`

### How to `pull` correctly

- Before turning to `pull`, let's make clear what a fast-forward merge is.

- __Fast-forward merges__
    - A fast-forward merge is the special case where a merge can be completed without creating an extra merge commit.
    - See the VGR or <https://sandofsky.com/images/fast_forward.pdf>

- __`pull` vs `pull --rebase` vs `pull --ff-only`__
    - What's the difference between `pull` and `pull --rebase`? (spoiler: `pull --rebase` > `pull`):
        - [When should I use `git pull --rebase`?](https://stackoverflow.com/questions/2472254/when-should-i-use-git-pull-rebase)
        - And another article discouraging `pull`: <https://adamcod.es/2014/12/10/git-pull-correct-workflow.html>
    - `pull` is actually considered harmful!
        - The preferred way to get remote changes is: Use `ull --ff-only` and if it fails __consciously take appropriate actions__ with merge, rebase, cherry-pick, whatever.
        - Read the answers to this [SO question](https://stackoverflow.com/questions/15316601/in-what-cases-could-git-pull-be-harmful)

## Workflow

- In order to have a broad understanding of Git let's have a look at a couple of popular usage paradigms
    
    - A very basic introductory article on how to use branches in Git: <https://sandofsky.com/blog/git-workflow.html>
    - [The Git flow](https://nvie.com/posts/a-successful-git-branching-model/). A very popular branching model for git.
    - Maximum historical innformation

    - [An overview of Git workflows](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/gitworkflows.html)
    
    - [Distributed Git Workflows](https://git-scm.com/book/id/v2/Distributed-Git-Distributed-Workflows)
        - Example of a centralized workflow: Gitlab's Merge Request workflow
        - Example of a Integration-Manager Workflow: [Fork and Pull Request Workflow](https://github.com/susam/gitpr) (GitHub's Pull Request workflow)
        - Example of a Dictator and Lieutenants Workflow: The Linux kernel's patch-based workflow

## On the importance of worrying about your commit history
- "Keep a clean Git history" they say
- [How (and why!) to keep your Git commit history clean](https://about.gitlab.com/2018/06/07/keeping-git-commit-history-clean/)
- `git rebase -i`
        - [Git Interactive Rebase, Squash, Amend and Other Ways of Rewriting History](https://robots.thoughtbot.com/git-interactive-rebase-squash-amend-rewriting-history)

- Undoing things in Git
    - `reset` / `commit --amend`
    - <https://hackernoon.com/when-to-use-git-reset-git-revert-git-checkout-dc4824795d9>
    - <https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting>

- `squash` / `commit --fixup` / `rebase --auto-squash`
    - <https://robots.thoughtbot.com/autosquashing-git-commits>
