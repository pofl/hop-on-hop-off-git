# The hop-on-hop-off guide to git

This guide is intended to be your guiding light in the dark dangerous cave of learning Git.

Goals of this guide:

- Help you improve your git skills. No matter how much you already know about git, here you can find new things to learn.

- You know the basics of git / SCM but you also know that you don't know enough. This guide lays out the track from "I know how to merge branches" to git mastery.

- For every little facet and detail of using git there exists a blog post or StackOverflow question or both that explain that particular topic very well. Instead of re-writing everything this guide stays concise and links to the full explanations.

This guide comes in two parts. Firstly, the [__guide__](https://github.com/pofl/git-guide/blob/master/docs/guide.md) itself, and secondly, a sort of [appendix](https://github.com/pofl/git-guide/blob/master/docs/rest.md), where I'll dump additional links and information in a less structured form.

[__Click here to see the guide__](https://github.com/pofl/git-guide/blob/master/docs/guide.md)

### Target audience

You should fall into one of these categories:

- You're already __familiar with Git to some extent__.
    - This guide is for you. To continue we assume you know everything listed in the next chapter. If you do not know something listed there, google the words that don't sound familiar to you.

- You're __new to Git__ and/or Version Control Systems in general.
    - In this case you're better off reading a book about Git and after that return to this guide.
        - Here is a comprehensive StacḱOverflow question+answers that covers the basics of Git and includes a list of books and guides for beginners: <https://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide>
        - Here is a beautiful git command reference: <https://ndpsoftware.com/git-cheatsheet.html>
        - Here is an incomplete list of git books/guides: <https://hackr.io/tutorials/learn-git>
        - [GitHub's Git learning resources](http://try.github.io/)

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
