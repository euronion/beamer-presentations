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
:::: column{width=60%}

> "Git  
> ... version-control system  
> ... tracking changes ... .  
> ... designed for coordinating work  
> ... in any set of files.  
> ... goals include speed, data integrity ...  
> support ... non-linear workflows."  

::::
:::: column{width=40%}

![](pictures/1920px-Git-logo.svg.png){width=70%}

::::
:::

Sources: [Wikipedia][6], [git-scm][1].

## Git can be

::: columns
:::: column{width=60%}

* great
 
* powerfull
 
* complex

* **helpful**

::::
:::: column{width=40%}

![](pictures/1920px-Git-logo.svg.png){width=30%}

[Source: git-scm][1]

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

(Backup: For the talk we will assume that we always use a remote repository like GitHub or GitLab.)

* Remote repository where you keep a copy of your files
* Hosted options available, famous ones e.g. GitHub and GitLab
* You can host your own, e.g. GitLab
  * It is also easy to switch between repositories
  * (it is all the same software)

:::

## Things to note

* Open Source
    - Try it for free
    - Great ecosystem: Clients, Onlinerepositories, Community
    - Persistent (no vendor lock-in)
* Easy to move repositories (`git clone` -- that's it)
* Millions of users world wide
* It is alive

::: notes

* Reap the benefits of open source software
* Well established in different communities (primarily SW development)
* It is alive:
  * There is no vendor dependency
  * No dependency on single persons
  * It is an living system supporting this product
  * Will probably life longer than the storage medium you might be using git on

:::

## How to use?

* Local client
* Interfaces:
  * Command line
  * GUIs
    * GitHub Desktop (works with any git)
    * gitGUI (included with `git` distro)
    * emacs / vim extensions available
* See: [git GUI Clients](https://git-scm.com/downloads/guis/)

 
# Terminology

* [gitglossary](https://git-scm.com/docs/gitglossary)

## Commit

* Commit = Snapshot = Version
* commit = save the current state as a snapshot

## Repository

This is where it all happens and is stored: `git init`

* Your files
* Git files
* Locally or remote

## Remote - Just another repository

* Like your local repository
  * A colleagues computer
  * A pen drive
  * An institutes server
* Easy places to start:
  * [GitLab](https://gitlab.com/)
  * [GitHub](https://github.com/)
* To interact:
  * `push`: changes from your local repository to a remote repository
  * `pull`: changes from a remote repository into your local repository
  * Pull request: Ask someone to merge your changes into their repository

## Log

Written history of all your commits (versions): `git log`

* Revert changes
* Access a previous commit / version
* Compare commits for changes

## Branches

Taking a different route at a crossroad:
If you start working on something new

* You can easily combine ("merge") it later: Partially or completley
* Separate completed work (your main branch) from developing content (other branches)
* Fast and simple way to keep things organised


# How does it work?

## A simple git workflow

![](pictures/02-git-commands.png){width=60%}

Source: [Tom Blount][3].

## Working with others (1)

::: columns
:::: column

> Avoid this -->

* Keep track  
 
* Keep it structured  

* Don't forget anything  

::::
:::: column

![](pictures/phd-comics_not-final-doc.gif){width=60%}
[Source: PhD comics.][5]

::::
:::

## common repository (1)

::: columns
:::: column
Setup a remote repository for everyone to access
::::

:::: column
![](pictures/collab_1-setup-repo.png)
::::
:::

## Issues

::: columns
:::: column
Report problems, discuss possible changes
::::

:::: column
![](pictures/collab_2-issues.png)
::::
::: 

## Pull requests

::: columns

:::: column
Suggest, discuss and combine changes
::::

:::: column
![](pictures/collab_3-prs.png)
::::

:::

## Branches

::: columns
:::: column
Features and major changes before finalising them in the `master` branch
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

## Working with others (2)

- Remote repositories/Platforms (GitHub, GitLab, ...)
- 1 branch per person/topic
- Ask to include changes (Pull requests)
  - Review
  - Merge changes from multiple people
- Be happy

## More features: Branches and merging

- Branches: Here we do our work
- Merging: For joining changes
- Merge conflicts: Happen rarely, but can be manually resolved
    * This is where good commit messages are helpful
    * Might want to check back with the person responsible for the changes

## Staying in control

- Pull request: "I changed something, please adapt it"
    * Maintainers can decide if it is included or not
- Growing and larger projects:
    * A few persons in charge of maintaining
    * Not so interesting for small projects
    * This is were you should set certain standards (naming, commit behaviour, content checking/code testing, ...)

## Good practices

* Commit often
* Good commit messages
* Use branches for changes, merge in master when change is complete
* Discuss workflow (commit, test/review, merge) with team


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

## Installation and Instructions

::: columns
:::: column{width="50%"}

![](pictures/qr-code.png){width=60%}

https://t1p.de/0mzx

::::
:::: column{width="50%"}

![In case of fire](pictures/in-case-of-fire-1-git-commit-2-git-push-3-leave-building2.png)
Source: [Marco Leong][4].

::::
:::

# Story to tell

# Advantages

* Track history of file changes
* Document motivation for changes
* Hosted repository:
  * Code is easier to (re-) discover
  * ... and will probably not get lost (w/ leaving PhD students)

## Similar software

* Mercurial (e.g. Bitbucket)
* Subversion SVN
* Bazaar
* Many more [(see this list)][2]

**Use whatever works for you, but use something and stick w/ it**


- Abgrenzung gegen andere Systeme
- Aktivierung durch Publikumsfrage
    * Eingaben durch Publikum. wer schon gearbeitet? Erfahrungen? Wieder?

- Vorteile
    * Wieder auffindbar
    * Dokumentiert

- Lokale Repositories und internet-Repositories?

- Projekte vorstellen:
    * Wer nutzt git? Panda/Cern, OpenMod
    * Firmen/Unternehmen
    * Verschiedene Branchen

- Best practices, further reading
- Wie stabil ist git / etabliert / gut?
    * Open Source
    * 15+ yrs entwickelt + stabil


> From https://en.wikipedia.org/wiki/Git
> Naming
>
>Torvalds quipped about the name git (which means unpleasant person in British English slang): "I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'git'." The man page describes Git as "the stupid content tracker". The readme file of the source code elaborates further:
>
>    The name "git" was given by Linus Torvalds when he wrote the very first version. He described the tool as "the stupid content tracker" and the name as (depending on your way):
>
>        random three-letter combination that is pronounceable, and not actually used by any common UNIX command. The fact that it is a mispronunciation of "get" may or may not be relevant.
>        stupid. contemptible and despicable. simple. Take your pick from the dictionary of slang.
>        "global information tracker": you're in a good mood, and it actually works for you. Angels sing, and a light suddenly fills the room.
>        "goddamn idiotic truckload of sh*t": when it breaks


# Take away

## git + GitHub/GitLab

::: columns

:::: column

* better file versioning
* better file exchange
* Less mistakes
* Better collaboration
* Traceability and accountability
* Great new ways to work together

::::

:::: column

Special thanks to Julika Mimkes SUB Göttingen

::::
:::

>> Use version control (git) - The future will thank you.

## License

Unless otherwise stated and other licenses apply (c) Johannes Hampp, 2019.

Graphics and text for which not other attribution is given are licensed unter Creative Commons Attribution 4.0 International Licence (CC BY 4.0).

![](pictures/cc-by.png)

## References

[1]: http://git-scm.com/downloads/logos
    "By Jason Long, CC BY 3.0"

[2]: https://en.wikipedia.org/wiki/List_of_version-control_software#Open_source_3
    "see this list of version-control software"

[3]: http://tomblount.co.uk/version-control/
    "Tom Blount, CC-BY-NC-SA"

[4]: https://hikaruzone.wordpress.com/2015/10/06/in-case-of-fire-1-git-commit-2-git-push-3-leave-building/
    "Marco Leong, CC-BY-NC 4.0"

[5]: http://phdcomics.com/comics/archive.php?comicid=1531
    "jorge cham"

[6]: https://en.wikipedia.org/w/index.php?title=Git&oldid=885739135
    "Wikipedia - Git"