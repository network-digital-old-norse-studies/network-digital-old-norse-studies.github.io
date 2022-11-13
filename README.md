# network-digital-old-norse-studies.github.io
Github Pages Repo for the Research Network for Digital Old Norse Studies

This repository holds the content of the [GitHub Pages](https://network-digital-old-norse-studies.github.io/) of the
Research Network for Digital Old Norse Studies.


## Interested?

If you're interested in the research network, see our [pages](https://network-digital-old-norse-studies.github.io/) for
more information. Or get in touch with one of the network members.


## How to Contribute to the Pages

The pages are built with [Hugo](https://gohugo.io/) and deployed using GitHub actions. This should make usage and
contribution quite simple. However it still requires some understanding of working with Git and how to use Hugo.
The following section should provide you with all necessary information.


### Working with Git

All members of the network (i.e. of the GitHub Organization representing our research network) are authorized to 
contribute to this repository. Other users can still fork the repository and open pull requests.


#### Working locally vs. on GitHub

Git is typically designed to work locally. If you do not want to do the setup for working locally, you can still do most
things online on GitHub. You may find though, that things are a bit "fiddly" and tooling is not as good as when working
locally. Also, running the in-progress version of the Hugo page (as described below) will not be possible when working
online.


#### Local Setup

Firstly, you must ensure that Git is installed on your computer. Verify this by typing `git --version` into your
terminal. If you see a version number, not an error message, you're good to go.

Git by itself is a command line tool, which means all the work is done by typing command into the terminal. As this is
not the working mode most people are comfortable with (and it's relatively error prone), I would recommend using a Git
client application with a nice user interface, like [GitHub Desktop](https://desktop.github.com/) (or any other 
application you like).

> Note: When using git commands in the terminal, the terminal _must_ be opened at the specific directory where your repo
> is located.

Next, you need to clone the repository to your computer. Execute 
`git clone https://github.com/network-digital-old-norse-studies/network-digital-old-norse-studies.github.io.git` or use
the `clone` command of your client application.

The first time after cloning, you also need to initialize the git submodule (which contains the theme of our page). This
is done by executing `git submodule update --init --remote --recursive`. Most git client applications do not support
this operation, so this should be done in the terminal.

In order to keep your local repository up to date with the repository on GitHub, you should always do a `git pull` when
there are changes in the remote repo. This can easiest be done in the client application.

When you have done meaningful changes to the repo, you have to stage the changes (though most clients let you skip that
step) and commit them. You have to provide a commit message, which should explain what you changed and which will show
up in the history of the repository. When committed to your local repository, you still need to push the changes to the
origin. Again, this is all easiest, using a client application.


#### Git Branching and Workflow

The GitHub pages are deployed from the `main` branch on. It is therefor essential that only valid states of the pages
are committed to this branch. Furthermore it's best to keep the git history as clean and readable as possible. Therefor,
branches should be merged into `main` using the `squash merge` workflow. The merge commits must have a meaningful commit
message.

Before starting to work, create a new branch. This can be done on GitHub or in your local repo. For the branch name, use
only lower case ASCII characters or digits, no special characters or signs, and replace spaces with hyphens (`-`). Keep
the branch name short and indicate what you want to do with the branch (e.g. `add-about-page`,
`update-outdated-affiliations` or `add-website-launch-post`), use present tense and imperative mood (not past tense or 
3rd person). Some people like to prefix branch names with `wip/` to indicate that it's a work in progress branch.

When working on your branch, you can commit as often as you like. This will allow you to revert to past commits if
you're not happy with your changes. But remember never to commit anything you're not comfortable to post on the 
internet: git remembers its entire commit history, even if you manually revert something in the next commit. Remember to
push your changes to github regularly, after pushing they are backed up in the cloud.

Once you're satisfied with the changes you made in your branch, you can open a "Pull Request" (short PR) on GitHub. A PR
needs to be reviewed by at least one member of the network other than the author of the changes. This serves to ensure
that only valid states of the repo are merged to the main branch, by enforcing a second pair of eyes to look over it; it
will also reduce the number of typos that slip through. Once review is through, the PR can be merged into the main
branch. This will apply the changes and automatically trigger a workflow to re-deploy the new version to the pages.  
The PR should be merged using the `squash merge` option, and the commit message should be descriptive of the changes
introduces by the PR - it will show up in the history of the main branch.


#### Deployment of the Pages using GitHub Actions

<!-- TODO: write short text here -->

### Using Hugo

<!-- TODO: write some chapters here, on how to set it up, run it, use it; and about markdown -->


### Any questions...?

If you still have any questions, don't hesitate to ask Balduin or anyone from "team tinkering".
