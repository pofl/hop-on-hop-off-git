# The guide to learning Git

This guide is intended to be your guiding light in the dark dangerous cave of learning Git.

Goals of this guide:

- Help you improve your git skills. No matter how much you already know about git, here you can find new things to learn.

- You know the basics of git / SCM but you also know that you don't know enough. This guide lays out the track from "I know how to merge branches" to git mastery.

- For every little facet and detail of using git there exists a blog post or StackOverflow question or both that explain that particular topic very well. Instead of re-writing everything this guide stays concise and links to the full explanations.

### Target audience

You should fall into one of these categories:

- You're already __a little familiar with Git__.
    - This guide is for you. To continue we assume you know everything listed in the next chapter. If you do not know something listed there, google the words that don't sound familiar to you.

- You're __new to Git__ and/or Version Control Systems in general.
    - In this case you're better off reading a book about Git and after that return to this guide.
        - Here is an incomplete list of git books/guides: <https://hackr.io/tutorials/learn-git>

### Motivation

I had a hard time learning Git. The first time I worked with Git, I wanted to get something done and git was an obstacle in my path to achieve a goal. I rushed the learning process. I got the basic commands down like add, commit, checkout, push etc. but then I stopped going deeper and I ended up in a pretty lost place.

__Learning git takes time__. There are entire books about git that take you from the basics to the details. However, I wasn't patient enough to read those books. I already knew the basics so why would I read a book that teaches me the basics all over before it gets to the good parts? And if I skipped to the good parts what small details will I have missed that would be necessary to get a good understanding?

## Prerequisite knowledge of Git

This guide will not cover any of the following topics. It assumes the reader knows these.

- Setting up a new repository

    - `git init`

- What are commits and how to commit

    - Terminology: commits, index/stage, working directory
    - Commits are identified by a unique hash which can be referred to with as little as its first six characters
    - Commands: `status` / `add` / `commit` / `log`

- What are branches and how to use them

    - `diff`
    - `branch` / `checkout` / `merge`

- Beyond a local repo on your computer

    - `clone` /  `remote`(s)
    - `push` / `fetch`

## Becoming proficient with Git

### [The Visual Git Reference (VGR)](http://marklodato.github.io/visual-git-guide/index-en.html)

- This is the mother of all informative resources about Git. Read it very carefully.

### A Git repository is a directed acyclic graph (DAG) of commits

- The commit DAG is frequently reported to be "the most important thing to realize about git". You should strive to _understand every git command in terms of how it manipulates the commit graph!_ The VGR is an excellent resource to understand this.
- Have a look at the DAG of your repository with `git log --all --decorate --oneline --graph` (log adog / _"look, a dog!"_)
- What you need to internalize is that __commits are nodes in a DAG__. All commits have one parent commit, merge commits have two parents.
- Another concept you need to understand are references. __Branches, tags and HEAD are all references__. Which basically means they are an alias of a particular commit.
- Examples: "`merge`creates a commit with two parent commits", "`cherry-pick` takes a list of commit hashes and applies them as patches onto HEAD" and "`reset` takes a reference to or the hash of a commit and makes the current branch point to it".
- [HEAD is a special reference](https://blog.thoughtram.io/git/rebase-book/2015/02/10/understanding-branches-in-git.html).
- [Relative references](https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git), like `HEAD~2` are very helpful too.

### Rebasing

- Rebasing is an alternative to merging in that both of them are ways to integrate two branches. A `rebase` is a special case of `cherry-pick`.

#### `cherry-pick`

- Select commits by their hashes and apply them one-by-one onto HEAD
- See the VGR for visual aid.

#### `rebase`

- Rebase does the same as cherry-pick, only for entire branches automatically. The VGR explains the technical side of rebases pretty well.
- This guide -- [Getting solid at Git rebase vs. merge](https://medium.com/@porteneuve/getting-solid-at-git-rebase-vs-merge-4fa1a48c53aa) -- explains in depth and in length the ins and outs of rebase in contrast with merge. It's very lengthy and also goes into many details that will be covered later in this guide. You should probably skip this and revisit it later.

#### `push --force` / `push --force-with-lease`

- After you rebased a branch it contains different commits than before. Because of that `git push` will reject your changes.
- A full explanation of the problem and why `--force-with-lease` is a better solution than `--force` can be found [here](https://developer.atlassian.com/blog/2015/04/force-with-lease/).

### Working with remotes

- `git fetch --all`
    - [`git pull --all`](https://stackoverflow.com/questions/4318161/can-git-pull-all-update-all-my-local-branches) will not pull all branches
- `push --set-upstream`
- `git branch -vva`

#### How to `pull` correctly

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

### Workflow

- In order to have a broad understanding of Git let's have a look at a couple of popular usage paradigms
    
    - A very basic introductory article on how to use branches in Git: <https://sandofsky.com/blog/git-workflow.html>
    - [The Git flow](https://nvie.com/posts/a-successful-git-branching-model/). A very popular branching model for git.
    - Maximum historical innformation

    - [An overview of Git workflows](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/gitworkflows.html)
    
    - [Distributed Git Workflows](https://git-scm.com/book/id/v2/Distributed-Git-Distributed-Workflows)
        - Example of a centralized workflow: Gitlab's Merge Request workflow
        - Example of a Integration-Manager Workflow: [Fork and Pull Request Workflow](https://github.com/susam/gitpr) (GitHub's Pull Request workflow)
        - Example of a Dictator and Lieutenants Workflow: The Linux kernel's patch-based workflow

### On the importance of worrying about your commit history
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

## A collection of _git aha moments_

## Mastering Git. Beyond what you need to know.

- `HEAD~1`

- `git add --patch`

- `rebase` with `-p` and `-r`

- [Git Internals by Scott Chacon](https://github.com/pluralsight/git-internals-pdf) (how git works internally)

- diff
    - word-diff
    - dir-diff

- blame and `git log --follow -- filename`
    - <https://stackoverflow.com/questions/3701404/list-all-commits-for-a-specific-file>

- Configuration
    - git log
        https://stackoverflow.com/questions/1057564/pretty-git-branch-graphs/35075021
    - Aliases
    - [How to keep git log and less output on the screen](http://serebrov.github.io/html/2014-01-04-git-log-and-less-keep-output.html)
    - difftool, mergetool
        - <https://developer.atlassian.com/blog/2015/12/tips-tools-to-solve-git-conflicts/>
    - tig
        - <https://www.atlassian.com/blog/git/git-tig>
    - lazygit
        - <https://github.com/jesseduffield/lazygit>

- 'Detached HEAD'
    - HEAD is a reference. It points to a commit like any other reference. The commit it points to will become the parent if you create a new commit.
    - Most of the time HEAD will point to a commit via pointing to a branch. If that is the case the behavior of `commit` will be that on top of making the current commit the parent of a new commit, also, the pointed-to branch reference will be set to the new commit. This is the default behavior as you know it.
    - However at times HEAD will point to a commit directly, not via another reference. This case if called 'detached HEAD' i.e. there is no branch attached to head. And new commits will not be retrievable through traversing the commit graph.

- `reflog`

- `cherry-pick`

- <https://stackoverflow.com/questions/4044368/what-does-tree-ish-mean-in-git>