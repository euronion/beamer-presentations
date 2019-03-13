---
author: Johannes Hampp
title: "Versioning and collaboration:"
subtitle: "git in research and beyond"
date: "Hacky Hour | DPG spring meeting Rostock | 14.03.2019"
institute: "Center for International Development and Environmental Research"
theme: jlug
---

# Intro

## File versioning: Why?

### Programme code, TeX, text documents, `.csv` data, ...

* Keeping track  
 
* Keep a copy  
 
* Keep your work safe  

::: notes

Keep track and a copy of your files
don't get mixed up or loose your progress
like a better backup

:::

## What's wrong with

### This works, right?
* E-Mail  
* Shared folders  
* USB sticks  
* Folder structure
`version1, version2, version3, ... versionFINAL, versionLAST`  
* Dropbox/Google Drive/Nextcloud  

# Let's be honest: It doesn't

::: notes

* If you have ever started off as a new PhD student
    and wanted to continue your predecessors work
* If you are trying to find recording and previous
    versions of the code you used for your paper a couple of months ago
* If you are trying to work on the same simulation code (e.g.)
    and you make daily changes.

It's bad. But what else is there to it?

:::

## We can do better

::: columns
:::: column

### Use the right tool for the job

* Source code  
 
* Thesis/Papers  
 
* any other plain-text file  

::::
:::: column
![](pictures/phd-comics_not-final-doc.gif){width=90%}

[Source: PhD comics.][5]
::::
:::

::: notes

There are many tools out there from people who faced these problems.
They are great tools for exactly these tasks.
For this case, there is a better tool we can use.
So let's use the right tool to do this job.

It doesn't matter if you are working on source code for R, Python, Fortran or
Matlab. It could also be your thesis or a paper you are preparing in latex.
Or even this presentation - you'll get a link later.

For collaborating on text documents (Word, OpenOffice, ...)
or other non-plain text files, then it is probably not the right tool.
But you can at least include them in the process, although you can only use
some of the essential features, but not all of them.

:::

# Git

## What do we ~~git~~ get

::: columns
:::: column

![](pictures/1920px-Git-logo.svg.png){width=50%}

::::

:::: column

"Git  
... version-control system  
... tracking changes ... .  
... for coordinating work  
... any set of files.  
... speed, data integrity  
... support non-linear workflows."  

::::
:::

Sources: [Wikipedia][6], [git-scm][1].

## Git can be

::: columns
:::: column

![](pictures/1920px-Git-logo.svg.png){width=50%}

[Source: git-scm][1].

::::

:::: column

* great  
* powerfull  
* complex  
* **helpful**

::::
:::

## Offers

* File versioning
  * History: View and go back in time
  * Compare file versinos
  * Blame: Who changed what?
  * Messages: And why?
* Exchanging files and collaborate
  * Combine changes (merge)
  * Compare changes (diff)
  * Avoid conflicting changes
* Easy way to backup

::: notes

What does it offer?
File versioning, so it allows you to look at different versions of files,
see how they changed in the past. Compare versions to find out what was changed.
And determined who did the change. If they are good you can find out, why they changed
it, because they left a good message with the change behind.

If you use a repository others can access as well, like a hosted repository,
then your code will be easier to (re-) discover -- maybe after 5 or 10 years.
At least it will be more difficult to get lost, especially when a PhD student leaves your group.
Stuff is easier to find again and documented -- isn't this what we usually want to embrace as scientists?
Aktivierung durch Publikumsfrage: Eingaben durch Publikum. wer schon gearbeitet? Erfahrungen? Wieder?

* Remote repository where you keep a copy of your files
* Hosted options available, famous ones e.g. GitHub and GitLab
* You can host your own, e.g. GitLab
  * It is also easy to switch between repositories
  * (it is all the same software)

:::

## Good to keep in mind

::: columns

:::: column

![](pictures/google-trends-git.png)

Source: Google Trends.

::::
:::: column

#### Open Source

* Ecosystem: Clients, Onlinerepositories, Community
* Available & Reliable
* Easy to move repositories:  
    (`git clone` -- that's it)
* Millions of users world wide
* It is alive

::::
:::

::: notes

Git is Open Source software, reap the benefits of open source software.
That is, you can be sure that it will be accessible for you in the future,
the software is nearly 15yrs. established and has a large community and good ecosystem.

* Well established in different communities (primarily SW development)
* It is alive:
  * There is no vendor dependency
  * No dependency on single persons or a single vendor
  * Makes it reliable and prevents vendor lockin
  * Also in the future will be alive
  * (and if only because many people depend on it)
  * I don't know how the DFG / archiving guidelines see it for 10yrs.
    archiving duties, but that's just a side note and not the sole reason to use it
  * It is an living system supporting this product
  * Will probably life longer than the storage medium you might be using git on

:::

## Using it daily

* Local client  

* Command line  
 
* GUIs  
  * GitHub Desktop (works with any git)
  * gitGUI (included with `git` distro)
  * emacs / vim extensions available

[Link: git GUI Clients](https://git-scm.com/downloads/guis/)

 
# Terminology \ (to help you get started)


## Commit

* Commit = Snapshot = Version  

* Current state saved as snapshot

## Repository

* Your files  

* Git files  

* Locally or remote  

This is where it all happens and is stored: `git init`

## Remote (repository)

* Just another repository  

* Like your local repository  
    (local computer, pen drive, server, ...)  

* Easy places to start:
  * [GitLab](https://gitlab.com/)
  * [GitHub](https://github.com/)  
 
* To interact:
  * `push`: changes from local --> remote
  * `pull`: changes from remote --> local
  * "Pull request": Ask someone include your change into their repository

## Branches

Alternativ story:
If you start working on something new

* Try stuff out  
 
* Easily combine it later: Partially or fully  
 
* Separate finished work ("main") from development  

* Fast and simple: Keep things organised

## Log

Written history of all your commits (versions): `git log`

* Revert changes  

* Access a previous commit / version  

* Compare commits for changes


[Link: gitglossary for more](https://git-scm.com/docs/gitglossary)

# How it works

## A simple git workflow

![](pictures/02-git-commands.png){width=60%}

[Source: Tom Blount][3].

## Working with others (1)



::: columns
:::: column

> Avoid this -->  

### Challenges

* Keeping track  
 
* Keeping a structured process  

* Don't forget anything  

::::
:::: column

![](pictures/phd-comics_not-final-doc.gif)

::::
:::


## Working with others (2)

::: columns
:::: column
1. Setup a common repository \
    (GitHub, GitLab, ...)
::::

:::: column
![](pictures/collab_1-setup-repo.png)
::::
:::

## Working with others (3)

::: columns
:::: column
2. Issues: Report problems, discuss possible changes
::::

:::: column
![](pictures/collab_2-issues.png)
::::
::: 

## Working with others (4)

::: columns

:::: column
3. Pull Requests: Suggest, discuss and combine changes
::::

:::: column
![](pictures/collab_3-prs.png)
::::

:::

## Working with others (5)

::: columns
:::: column
4. Use branches for features and major changes:  
   only after finalising merge them to your `master` branch
::::

:::: column
![](pictures/collab_4-branches.png)
::::

:::

::: notes
* Branches are a way of organising your work.
* If you are working on your own little project, you might not need to use branches at all...
* ... but they help in organising things.
* You bundle multiple changes / commits and put them in a new branch.
* For code that is when you want to for example try out something new
  * Don't comment out stuff and recompile
  * Create a new branch (it is fast and cheap in terms of ressources!)
  * Make the changes to the code, you can also commit them
  * Just try out the new code
  * If you don't like it, delete the branch and go back to your old one (your previous changes don't need to be manually reversed)
  * Or check what else you changed and keep an overview - especially when changing at a lot of places your code.
* When collaborating with others, you normally want to work on your own branch and only when finishing a piece of work you want to share with others, you then merge your branch into the `master` branch of all collaborators.
:::

## Rules when collaborating

### You should have some, e.g.

* 1 branch per person/topic  

* have maintainers, not only contributors  

* Merge conflicts can happen  

* --> Look for best practices  

* **Be happy**  

::: notes

Review code suggestions before including them.
Don't allow everyone to add code as they want,
but have a few responsible maintainers, which decide if changes
work with the existing content or need to be adjusted first.

* Merge conflicts: Can happen, when multiple people work on the same
    content, but don't worry. Git will help you with getting around this as well.
    Trust the tool ;-).

* Staying in control for larger projects:
  * not as important for small collaborations (but always a good idea)
  * for pull request: "I changed something, please adapt it"
    * Maintainers can decide if it is included or not
  * Growing and larger projects:
* This is were you should set certain standards (naming, commit behaviour, content checking/code testing, ...)

:::



## Some Good practices

* Commit often, rebase later  

* [Good commit messages! (Link)](https://chris.beams.io/posts/git-commit/)  

* Changes in branches, `master` when change is ready  

* Have a workflow -- and follow it  
  (commit, test/review, merge)

::: notes

In the document in the git repository there are also linked some good
and best practices for using git. Some are pretty general, so I suggest
looking at them briefly. Just write them down on a post it to remember
them daily.

:::

# Sweet Examples

## the obvious

`numpy` library for Python.

GitHub:
* Code
* Issues & discussion
* Code suggestions (Pull requests)
* Documentation

[Link: numpy](https://github.com/numpy/numpy)

## the small (and still obvious)

`atlite`, open source tool for energy system modeling.

GitHub:
* Code + ... (as w/ numpy)
  
also:
* scientific discussion
* different versions (reproducibility)
* different groups contributing openly

[Link: atlite](https://github.com/FRESNA/atlite)

## the crowd-science'd

`Deep review`, a crowd-sourced review paper.

* Written on GitHub
* Contributions openly accepted
* Contributions per author tracked
* Redacted versions and revisions
* 123 pages with 36 accepted authors
* authors accepted based on tracked contributions

[Link: Deep review](https://github.com/greenelab/deep-review)

::: notes
deep-review is a crowd-sourced review paper in for machine learning.

Is a nice example of new ways to write especially review paper but also
other work.

After given out the call, that they will be writing a review paper,
the initiating authors accepted contributions to the GitHub repository
from anyone. They reviewd the contributions and included them.
This way, the review spanned a great deal of topics with in the end 123 pages and 36 accepted authors.

The accepted authors were accepted based on their track record:
As the contributions per author can be tracked, any author passing a defined
threshold was accepted.

This is a great way of also making transparent, which author has how much
contributed to a publication.

:::

## Legal documents

Tracking changes to German legislation ("Bundes-Git")

![](pictures/bundes-git.png){width=50%}

[Link: Bundesgit](https://github.com/bundestag/gesetze)


::: notes
While not for itself as interesting for probably most of the people here,
this is another nice example of what we can use Git and GitHub for.

This repository contains many of laws and regulations valid in Germany.
The changes to each legilative document can be tracked, attributed to politicians and compared across a wide range of years.

Similiar things exist for people publishing their music on GitHub,
so you can watch how over time their songs developed ;-) .

Maybe you can also think of creative ways to use Git?
I have personally also heared of some universities trying to use git for
submitting, correcting and reviewing lab reports for students.
:::

# Hands-On

## Tutorials / Instructions

::: columns
:::: column

![](pictures/qr-code.png){width=60%}  
https://t1p.de/xdvc

::::
:::: column

![In case of fire](pictures/in-case-of-fire-1-git-commit-2-git-push-3-leave-building2.png)  
[Source: Marco Leong][4].

::::
:::

# Take away

## git (+ GitHub/GitLab)

* better file versioning  

* better file exchange  

* Less mistakes  

* Better collaboration  

* Traceability and accountability  

**Use version control (git) - The future will thank you.**  

*Special thanks to Julika Mimkes SUB Göttingen*

::: notes

There are also other systems than git.
In the end it boils down to the recommendation:
Use a version control software(!) system that works for you.
I suggest you select a system and try it out for yourself for a few days.
Then look back, select a system you liked and stick with it.
Or just learn to use git.

:::

## License

Unless otherwise stated and other licenses apply  
(c) Johannes Hampp, 2019.

Graphics and text for which not other attribution is given are licensed unter Creative Commons Attribution 4.0 International Licence (CC BY 4.0).

![](pictures/cc-by.png)

## References

[1]: http://git-scm.com/downloads/logos
    "By Jason Long, CC BY 3.0"

[3]: http://tomblount.co.uk/version-control/
    "Tom Blount, CC-BY-NC-SA"

[4]: https://hikaruzone.wordpress.com/2015/10/06/in-case-of-fire-1-git-commit-2-git-push-3-leave-building/
    "Marco Leong, CC-BY-NC 4.0"

[5]: http://phdcomics.com/comics/archive.php?comicid=1531
    "jorge cham"

[6]: https://en.wikipedia.org/w/index.php?title=Git&oldid=885739135
    "Wikipedia - Git"