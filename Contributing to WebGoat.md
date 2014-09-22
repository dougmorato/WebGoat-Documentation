## Overview

The WebGoat project is hosted on github, here [https://github.com/WebGoat]. Contributions are welcome!  This page describes the WebGoat development process. 

## Roles

* **Core WebGoat developers**. These folks have access to the WebGoat repository. They also have access to create, assign, and resolve JIRA tickets
* **Webgoat contributors**. These folks do NOT have access to WebGoat, and have either read-only or no access to JIRA 
* **WebGoat admins**. These folks have admin access to the WebGoat Bamboo, JIRA and github repos to approve new users

Webgoat admins ( Bruce right now ), promote users from "external" to "WebGoat" developers when it makes sense.

## Development Workflow for Core Developers

Master is the main working stream. it is built nightly in bamboo, and produces a new version.  This is the bleeding edge version, the 'nightly build'

Anything you merge to master needs to be at least good enough to go into the nightly build. that means:
1.          all of the tests pass
1.          nothing is _worse_ than it was before you started
It is strongly recommended that you create a local branch for any work you do. If you are working on a JIRA ticket, name the branch for it ( WEB-168).  When work is finished, you can do one of two things:
1.       Push the branch to origin, so that someone else can check it out to test/review
1.       Merge it into your local master branch, and then push the commits directly to master on origin.
Working directly on your clone of master is discourage, but acceptable.  This makes sense for very trivial changes that you know will not need review by others, and will be very quick.
Releases are cut from the master branch, using a separate, manually executed bamboo job. This job tags master, and produces a numbered release.  These artifacts are manually copied to the archive locations, especially stable releases.

## Development Workflow for Contributors 

1. Create a gihub account, if not already existing
1. Fork the webgoat repository on github
1. Create a topic branch for the changes. The most common will be a new lesson or new feature. Presumably, most contributors do not have access to JIRA, so it will be common that they do not name it for a JIRA case. If a contributor is coordinating with a Core developer on a JIRA ticket, using the JIRA ticket is helpful
1. After testing and verifying, contributor creates a pull request
1. Core developer checks out the requested branch, and tests. At this stage, a JIRA ticket may be created or found if it is applicable
1. If the changes look good, core developer either merges the pull request onto master or seeks review from other developers. If the changes are not ok, the contributor is notified with changes that are neccessary.

==Java source code formatting:==

WebGoat uses the Eclipse Editor with JavaStyle formatting.  The JavaStyle WebGoat XML file is located at [http://code.google.com/p/webgoat/source/browse/trunk/webgoat/main/project/config/JavaStyle_WebGoat.xml JavaStyle_WebGoat.xml].  

After building your Eclipse Project using the instructions at [http://webgoat.googlecode.com/svn/trunk/webgoat/main/HOW%20TO%20create%20the%20WebGoat%20workspace.txt How to Build Webgoat] 
  * Right click on the WebGoat project in the package explorer view
    * Select Java Code Style -> Formatter
    * Enable Project Specific Settings
    * Import -> Browse to config/JavaStyle_WebGoat.xml
    * OK

==Rules of the code base:==

WebGoat uses the 'The Branch-When-Needed' software management system as identified in the [http://svn.collab.net/repos/svn/trunk/doc/user/svn-best-practices.html subversion best practices document].

Users commit their day-to-day work on /trunk. 
{{{
    Rule #1: /trunk must compile and pass regression tests at all times.
             Committers who violate this rule are publically humiliated. 
    Rule #2: a single commit (changeset) must not be so large so as to
             discourage peer-review. 
    Rule #3: if rules #1 and #2 come into conflict (i.e. it's impossible
             to make a series of small commits without disrupting the
             trunk), then the user should create a branch and commit a
             series of smaller changesets there. This allows peer-review
             without disrupting the stability of /trunk.
}}}
Pros: /trunk is guaranteed to be stable at all times. 
      The hassle of branching/merging is somewhat rare.

Cons: Adds a bit of burden to users' daily work: they 
      must compile and test before every commit.