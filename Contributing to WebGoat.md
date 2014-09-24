## Overview

The WebGoat project is hosted on github, [here](https://github.com/WebGoat). Contributions are welcome!  This page describes the WebGoat development process. 

## Roles

* **Core WebGoat developers**. These folks have access to the WebGoat repository. They also have access to create, assign, and resolve JIRA tickets
* **Webgoat contributors**. These folks do NOT have access to WebGoat, and have either read-only or no access to JIRA.
* **WebGoat admins**. These folks have admin access to the WebGoat Bamboo, JIRA and github repos to approve new users

Webgoat admins promote users from "external" to "WebGoat" developers when it makes sense.

## Repository Setup and Release Process

Master is the main working stream. It is built nightly in bamboo, producing a numbered version each build.  This is the bleeding edge version, the 'nightly build'. The latest nightly build can be found [here](https://webgoat.atlassian.net/builds/browse/WEB-WGM/latest), and a list of all recently nighly builds is [here](https://webgoat.atlassian.net/builds/browse/WEB-WGM)

Anything you merge to master needs to be at least good enough to go into the nightly build. that means:

1.          all of the tests pass
1.          nothing is _worse_ than it was before you started

Releases are cut from the master branch, using a separate, manually executed bamboo job. This job tags master, and produces a numbered release.  These artifacts are manually copied to the archive locations, especially stable releases.

If you have access, [you can view the WebGoat builds](https://webgoat.atlassian.net/builds/browse/WEB)


## Development Workflow for Contributors 

Contributors do not have direct repository access, but that doesn't mean contributions are not welcome!  If you'd like to help out, just fork the Webgoat Repository and make a pull request.  In more detail:

1. **Create a gihub account**, if not already existing
1. **Fork the Webgoat repository** at https://github.com/WebGoat/WebGoat 
1. **Create a topic branch** for the changes. If you are working on a Webgoat JIRA issue, use the ticket number as the topic branch name. If there is no JIRA ticket, use a sensible name.
1. **Develop and test your changes**  to make sure your changes are ok
1. **Create a Pull Request**. When you are ready to contribute your code. This is done via the github website. Please rebase your commits on top of master, so that your changes are easy to pull. If you don't know how to do that, there is a good overview [here](https://github.com/edx/edx-platform/wiki/How-to-Rebase-a-Pull-Request)
1. **Core developer merges changes** If your changes look good, a care developer will merge the change into master.  Your changes will be available in the nightly build. If the changes needed more work, that is coordinated on the pull request thread.

If you are not an experienced git user, these tutorials might help:

* [Setting up Git](https://help.github.com/articles/set-up-git)
* [Forking a repo](https://help.github.com/articles/fork-a-repo)
* [About Pull Requests](https://help.github.com/articles/using-pull-requests)

## Development Workflow for Core Developers

The workflow for Core Developers is very similar to that of contributors. The main difference is that creating a fork is not necessary, and JIRA references are mandatory. Core developers, of course, may also be merging pull requests from external contributors.

Core Developers should follows these steps when working on issues:

1. **Create a topic branch** for the changes. Use the ticket number as the topic branch name. If there is no JIRA ticket, you should get/make one.
1. **Develop and test your changes** to make sure your changes are ok
1. **Push your changes to origin** This makes your branch available for others to review
1. **[Optional] Get Feedback, if needed** If you need someone else to test, they can check out your branch. If the change is simple, you might just move directly to the pull request.
1. **Create a Pull Request**. This is done via the github website.  When you think your changes are ready, make a pull request for the merge into master.  Though you could easily merge directly, this makes sure another developer knows about the change, and has reviewed it.  
1. **A Different Core developer merges changes** Your changes will be available in the nightly build. If the changes needed more work, that is coordinated on the pull request thread. It is preferred to merge pull requests through the github website, unless there are conflicts.  Not only is it easier, but it is less prone to error.
    *  If a pull request cannot be merged on the website, it is ok to ask the originator to rebase their pull request on master.  This is more work for the requestor, but it is almost always the right thing to do, because it will have the original author solving merge problems, not the reviewer.  If this is greek to you, [this might help](https://github.com/edx/edx-platform/wiki/How-to-Rebase-a-Pull-Request)
Though it is tempting, core developers should not work off of their local master branch to develop new features. There are two reasons why this is a bad idea:

1.       You wont be able to easily work on multiple things without stashing
1.       When your pull request is merged into the target branch, the person merging your pull request may decide to rebase your commits to avoid a merge commit, or to squash the commits into a single coherent commit. If your pull request was from your 'master' branch, you will encounter problems when merging the target branch back into your own 'master'. 

