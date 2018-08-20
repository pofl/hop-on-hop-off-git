This guide is intended to be your guiding light in the dark dangerous cave of learning Git.

Goals of this guide:

- Help you improve your git skills. No matter how much you already know about git, here you can find new things to learn.

- You know the basics of git / SCM but you also know that you don't know enough. This guide lays out the track from "I know how to merge branches" to git mastery.

- For every little facet and detail of using git there exists a blog post or StackOverflow question that explains that topic very well. Instead of re-writing everything this guide stays concise and merely introduces each topic shortly. It then gives you a couple of links to texts fully explaining it.

## Motivation

I had a hard time learning Git. The first time I worked with Git, it was an obstacle in my path to get something done. I rushed the learning process. I got the basic commands down like add, commit, checkout, push etc. but then I ended up in a pretty lost place.

__Learning git takes time__. There are entire books about git that take you from the basics to the details. However, I wasn't patient enough to read those books. I already knew the basics so why would I read a book that teaches me the basics all over before it gets to the good parts? And if I skipped to the good parts what small details will I have missed that would be missing to have a good understanding?



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

- `diff` / `log`
- `branch` / `checkout` / `merge`

#### Beyond a local repo on your computer

- `remote`s, `clone`
- `push` / `fetch`

### Becoming proficient with Git

- [__The Visual Git Reference__](http://marklodato.github.io/visual-git-guide/index-en.html)
    - 

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
    - [Fork and Pull Request Workflow](https://github.com/susam/gitpr) (GitHub's contribution workflow)
    - Getting a general idea of how to work with git: <https://sandofsky.com/blog/git-workflow.html> (but please respect our internal guidelines!)

- On the importance of worrying about your commit history
    - "Keep a clean Git history" they say
    - [How (and why!) to keep your Git commit history clean](https://about.gitlab.com/2018/06/07/keeping-git-commit-history-clean/)
    - `git rebase -i`

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

### A collection of _git aha moments_

### Mastering Git. Beyond what you need to know.

- `HEAD~1`

- [Git Internals by Scott Chacon](https://github.com/pluralsight/git-internals-pdf) (how git works internally)

- diff
    - word-diff
    - dir-diff

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

- `reflog`

- `cherry-pick`

- <https://stackoverflow.com/questions/4044368/what-does-tree-ish-mean-in-git>