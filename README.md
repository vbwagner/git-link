NAME
====

git-link -Git command to output links for commit

SYNOPSIS
========

**git link**

**git link** _commit_

DESCRIPTION
===========

**git-link** command when placed somewhere in your PATH, would be
invoked as **link** submcommand of **git**(1).

When invoked inside GIT repository, it outputs link to the web
interface of remote git site which displays specified commit. (or
current HEAD if none was specified).

You can specify any number of commit hash digits, which uniquely
identify commit. It would be canonized - output of format **%h** of
**git-show** used for link text and full hash in URL.

It outputs link in the
format useful to pasting into **JIRA** or **Confluence**. Feel free to
change this.

It recognizes two types of GIT web UI - **github** and **gitweb**.
**gitlab** for purposes of this scritp

Only **github.com** site is buildin into script. All other sites should
be described in **~/.git-link** configuration file

CONFIGURATION
=============

**.git-link** is INI-style configuration file. Its section headers are
canonical site names. There is obligatory parameter **webui** which
specifies UI type - **gitweb** or **github**.

For **gitweb** sites there are two extra parameters **urlprefix** and
**pathprefix** which specify what to strip from `git remote` output and
what to add to convert repository path to URL to web interface.

Field **priority** is used to choose right web interface in case you
have several remotes in your working copy. Site with minimal value of
priority would be choosen.

Field **aliases** list alternate names of the site which can be used
when repository is cloned.

FILES
=====

**${HOME}/.git-link** configuration file

SEE ALSO
========

**git**(1)

AUTHOR
======

Victor Wagner <vitus@wagner.pp.ru>


