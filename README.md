# The hop-on-hop-off guide to git

Part 1 - [The hop-on-hop-off Guide to Git](https://github.com/pofl/git-guide/blob/master/guide.md)
Part 2 - [Appendix](https://github.com/pofl/git-guide/blob/master/appendix.md) (still in Alpha)

Target audience: Advanced Git users who want to become experts with Git. This is not for beginners! See section _Target audience_.

Goals of this guide:

- Pick up advanced-beginner/semi-advanced Git users and give them a solid understanding of Gits inner workings and the range of user-available tools so that they become sophisticated and confident Git users.

- Instead of writing everything from scratch this guide is more of a guided tour of high-quality in-depth articles about various Git topics - a structured overview of topics to study. This guide is structured enough so you know what to prioritize on your studying path, while being brief enough so you can also make your own choices regarding which topics tostudy and which to skip.

## Motivation

I had a hard time learning Git. The first time I worked with Git, I wanted to get things done and git felt more like an obstacle than a tool. I rushed the learning process. I got the basic commands down like add, commit, checkout, push etc. but then I stopped going deeper and I ended up in a pretty lost place.

__Learning git takes time__. There are entire books about git that take you from the basics to the details. However, I wasn't patient enough to read those books. I started learning the basics in an unstructured way with lots of time-consuming googling. Later when I wanted to take my knowledge further, there was no point in picking up a book as every book covers the basics and goes from there. I already knew the basics so why would I read a book that teaches me the basics all over before it gets to the good parts? And if I skipped to the good parts what small details will I have missed that would be necessary to get a good understanding?

So that's why I created this hybrid of a guide and a collection of web articles. This guide is structured enough so you know what to prioritize on your learning path, while being brief enough so you can also make your own choices on what topics to skip.

## Target audience

- If you are already __familiar with Git to some extent__
    - This guide is for you. To continue we assume you know everything listed in the next section. If you do not know something listed there, google the words that don't sound familiar to you.

- If you are __new to Git__ and/or Version Control Systems in general
    - In this case you're better off reading a book about Git and after that return to this guide.
        - Here is a comprehensive StacḱOverflow question+answers that covers the basics of Git and includes a list of books and guides for beginners: <https://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide>
        - Here is a beautiful git command reference: <https://ndpsoftware.com/git-cheatsheet.html>
        - Here is an incomplete list of git books/guides: <https://hackr.io/tutorials/learn-git>
        - [GitHub's Git learning resources](http://try.github.io/)

### Prerequisite knowledge of Git

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
