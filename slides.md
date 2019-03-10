---
author: Johannes Hampp
title: "Versioning and collaboration:"
subtitle: "git in research and beyond"
date: "Hacky Hour | DPG spring meeting Rostock | 14.03.2019"
institute: "Center for International Development and Environmental Research"
theme: jlug
---

---

# File versioning: Why?

**What?**
* Keeping track
* Keep a copy
* **Keep your work safe**

Programme code, TeX and text documents, `.csv` data, ...

::: notes

Keep track and a copy of your files
don't get mixed up or loose your progress
like a better backup

:::

# What's wrong with...

* E-Mails
* Shared folders
* USB sticks
* Folders: `version1, version2, version3, ... versionFINAL, versionLAST`
* Dropbox/Google Drive/Nextcloud
  
**Nothing. But we can do better.**

# The right tool to ...

... do the job.

**Which files?**

* Source code
* Thesis/Papers
* any other plain-text file

::: notes
if you are working on text documents (Word, OpenOffice, ...)
or other non-plain text files, then it is probably not the right tool.
:::

# Motivation


## What do we ~~git~~ get?

:::::::::::::: {.columns}
::: {.column width="50%"}

> "Git is a distributed version-control system for tracking changes in source code during software development.
> It is designed for coordinating work among programmers, but it can be used to track changes in any set of files.
> Its goals include speed, data integrity, and support for distributed, non-linear workflows."
> (Wikipedia)

:::
::: {.column width="50%"}

![Git logo](pictures/1920px-Git-logo.svg.png)
Source: [^1]

:::
::::::::::::::

## So?

:::::::::::::: {.columns}
::: {.column width="50%"}

Git can be

* great
* powerfull
* complex

but most of all

* **helpful**

:::
::: {.column width="50%"}

![Git logo](pictures/1920px-Git-logo.svg.png)
Source: [1]

:::
::::::::::::::

## It offers

* Versioning of files
  * Go back in time (history)
  * Compare file versinos
  * Who changed what?
  * .. And why?
* Exchanging files
* Collaborate:
  * Combine changes
  * Compare changes
  * Avoid conflicting changes
* Easy way to backup(*)

(* For the talk we will assume that we always use a remote repository like GitHub or GitLab.)

::: notes

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

---
 
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

---

# How does it work?

## A simple git workflow

![Simple git workflow](pictures/02-git-commands.png){width=60%}
Source: [3].

## A simple git workflow

:::::::::::::: {.columns}
::: {.column width="50%"}

1. Init
2. Stage / add
3. Commit
4. Repeat 1. and 2.
5. Push

:::
::: {.column width="50%"}

![Simple git workflow](pictures/01-workflow.png)
Source: [3]

:::
::::::::::::::

## Working with others (1)

:::::::::::::: {.columns}
::: {.column width="50%"}

> **Avoid this**

* Keep track
* Keep it structured
* Don't forget anything

:::
::: {.column width="50%"}

![Source: [5].](pictures/phd-comics_not-final-doc.gif){width=75%}

:::
::::::::::::::

## common repository (1)

Setup a remote repository for everyone to access
![1-setup-repo](pictures/collab_1-setup-repo.png)

## Issues

Report problems, discuss possible changes
![2-issues](pictures/collab_2-issues.png)

## Pull requests

Suggest, discuss and combine changes
![3-PRs](pictures/collab_3-prs.png)

## Branches

Contain features and major changes before finalising them in the `master` branch
![4-branches](pictures/collab_4-branches.png)

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

---

# Sweet Examples

## the obvious

**`numpy` library for Python**

On GitHub:

* Code
* Issues & discussion
* Code suggestions (Pull requests)
* Documentation

[Link](https://github.com/numpy/numpy)

## the small (and still obvious)

**`atlite`, a Phython-based open source tool for energy system modeling.**

* Code + ... (as w/ numpy)
  
**but also**
* scientific discussion (science side of implementations)
* access to different versions (reproducibility)
* different groups contributing openly

[Link](https://github.com/FRESNA/atlite)

## the crowd-science'd

**Deep review**
A crowd-sourced review paper in machine learning.

* Written on GitHub
* Contributions openly accepted
* Contributions per author tracked
* Redacted versions and revisions available
* 123 pages with 36 accepted authors
* authors accepted based on tracked contributions

[Link](https://github.com/greenelab/deep-review)

---
# Hands-On

## Installation and Instructions
:::::::::::::: {.columns}
::: {.column width="50%"}
![QR code to GitHub repository](pictures/qr-code.png)
(https://github.com/euronion/beamer-presentations/blob/2019/dpg-rostock/material/README.md)
**Put a link to the repository with a README.md here**
:::
::: {.column width="50%"}
![In case of fire](pictures/in-case-of-fire-1-git-commit-2-git-push-3-leave-building2.png)
Source: [4].
:::
::::::::::::::

# Story to tell

## Advantages

* Track history of file changes
* Document motivation for changes
* Hosted repository:
  * Code is easier to (re-) discover
  * ... and will probably not get lost (w/ leaving PhD students)

## Similar software

* Mercurial (e.g. Bitbucket)
* Subversion SVN
* Bazaar
* Many more [2]

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
>Torvalds quipped about the name git (which means unpleasant person in British English slang): "I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'git'."[23][24] The man page describes Git as "the stupid content tracker".[25] The readme file of the source code elaborates further:[26]
>
>    The name "git" was given by Linus Torvalds when he wrote the very first version. He described the tool as "the stupid content tracker" and the name as (depending on your way):
>
>        random three-letter combination that is pronounceable, and not actually used by any common UNIX command. The fact that it is a mispronunciation of "get" may or may not be relevant.
>        stupid. contemptible and despicable. simple. Take your pick from the dictionary of slang.
>        "global information tracker": you're in a good mood, and it actually works for you. Angels sing, and a light suddenly fills the room.
>        "goddamn idiotic truckload of sh*t": when it breaks

--- 

# Conclusion

## Take away

git with GitHub/GitLab means

* More efficient file keeping
* Easier file exchange
* Less mistakes combining
* Better collaboration
* Traceability
* Great new ways to work together

> Use version control (git) - The future will thank you.

**TODO: Insert CC-BY-SA license**

**TODO: Special thanks to Julika Mimkes SUB Göttingen**


## References

[1]: By Jason Long - (http://git-scm.com/downloads/logos), CC BY 3.0.

[2]: see [List of version-control software](https://en.wikipedia.org/wiki/List_of_version-control_software#Open_source_3).

[3]: Tom Blount, (http://tomblount.co.uk/version-control/), CC-BY-NC-SA.

[4]: Marco Leong, (https://hikaruzone.wordpress.com/2015/10/06/in-case-of-fire-1-git-commit-2-git-push-3-leave-building/), CC-BY-NC 4.0.

[5]: jorge cham (http://phdcomics.com/comics/archive.php?comicid=1531).
