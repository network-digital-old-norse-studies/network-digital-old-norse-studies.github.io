# network-digital-old-norse-studies.github.io
Github Pages Repo for the Research Network for Digital Old Norse Studies

This repository holds the content of the [GitHub Pages](https://network-digital-old-norse-studies.github.io/) of the
Research Network for Digital Old Norse Studies.


## Interested?

If you're interested in the research network, see our [pages](https://network-digital-old-norse-studies.github.io/) for
more information. Or get in touch with one of the network members.


## How to Contribute to the Pages (Step by Step)

The basis of the pages are markup-files. If you want to understand how markup files are rendered as a web page, see the technical explanation below.
This section will give you brief explanation on how to edit what is visible to the public in a way that is almost as easy as writing in the text editor of your choice.

### Step One

The most important thing is to first create a branch in GitHub for your edit. This makes sure there is some form of editorial oversight and changes
can be reviewed before being published. You can find out how to create a branch [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository)

When creating a branch, give it a name like this: "wip/YOUR_BRANCH_NAME".

### Step Two

Edit the file in the branch you just created. You can do this locally or directly in the browser. All files are found in the folder "content".
Editiing markdown is very easy: You use "#" to mark headings and just wirte your text underneath. If you need more formatting options, check out
the resources listed in the section on markdown below.

### Step Three

Save the file and create a pull request. Write a short comment summarizing your edits. One of the admins will then read and review your PR.
You can find more information about pull requests and how to create one [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

That's basically it!


## How to Contribute to the Pages (technical version)

The pages are built with [Hugo](https://gohugo.io/) and deployed using GitHub actions. This should make usage and
contribution quite simple. However it still requires some understanding of working with Git and how to use Hugo; all 
content of Hugo is written in markdown.
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

Deploying the repo's content to the GitHub Pages is done using GitHub Actions. The process is fully automated and does
not require any attention from contributors (given all is set up correctly and nothing is broken). The action is
triggered by any merge to the main branch, and should only take a couple of seconds; sometime it takes several minutes
for the changes to be visible on the pages. If the changes still do not show up after some minutes, please check the
"Actions" tab on github to see if something failed. As the action is triggered by merging to main, it is crucial to
ensure that a pull request is up to standard before it gets merged - otherwise this will show up on the pages.


### Using Hugo

[Hugo](https://gohugo.io/) is a static site generator written in the Go programming language. It creates websites from
markdown files by applying the provided content and metadata to templates. This makes it extremely easy to create simple
but modern-looking sites with minimal effort and tech knowhow requirements.

For regular use cases, Hugo only has a notion of two basic concepts: Single pages and list pages. A single page
corresponds to a single markdown file. A list page gives overview over (and links to) multiple pages that are grouped.  
All markdown files have to be placed in the `content` directory, which corresponds to the home page of the website. Any
subdirectory therein will create a sub-route, for which a list page is automatically created; all markdown files will
resolve in a page using the filename (without file extension) as the page route, the only exception being the filename
`_index.md` which provides additional content to the list page of a route, if desired.  

For our page, we use the Hugo theme [Gokarna](https://github.com/526avijitgupta/gokarna), which additionally
distinguishes between "posts" and "pages". Pages can be any static page that is either included in a menu or linked to
by another page (like a wiki), posts are blog posts and are displayed in chronological order.

Our Hugo pages can be created by simply writing markdown files and letting GitHub actions take care of all the rest.
However it is more advisable to install Hugo locally, so that hugo may help you creating new pages, to see if it can
successfully process all the pages you have written, and to be able to check the generated website locally rather than
having to deploy first to see how the result will look.

When you're working in a text editor like [Visual Studio Code](https://code.visualstudio.com/), this comes with a
built-in terminal, so you have the Hugo command line tool handy while you're working on the pages.


#### Installing Hugo

Hugo is available for all operating systems. An installation guide can be found [here](https://gohugo.io/installation/).
The guide however recommends using command line package managers for installation - for Linux users this should feel
familiar, for Mac OS the homebrew package manager is very nice; for windows you can use chocolatey, and if you don't
like installing your applications through the command line, you can use it once to install
[Chocolatey GUI](https://community.chocolatey.org/packages/ChocolateyGUI), and then use the graphical user interface to
install Hugo (or any other application).

**Note:** If given the choice between `hugo` and `hugo-extended`, please install the extended version. Otherwise you may
be missing some features.

To verify that the installation worked, open a new terminal *after the installation finished* and type `hugo version`.
If you see something that resembles a version number rather than an error message, everything worked.


#### Creating new pages with Hugo

As mentioned above, in Hugo, content is written in simple markdown files, which can easily be created manually. However
you can also create new pages through Hugo, which will generate some metadata for you which you otherwise have to add to
the file yourself.

To create a new page, simply type `hugo new [PAGE-NAME]` and Hugo will create it for you. Pages are automatically
created in the `content` folder, a slash can be used to mark sub-folders; the file-ending `.md` is required.  
E.g.: `hugo new pages/about.md` would create the "about" page, `hugo new posts/website-launch.md` would create a blog
post to accompany the launch of our website.

The metadata added to the file by Hugo is delimited by three hyphens and consists of the three fields `title`, `date`
and `type`, plus the optional field `description`. Adjust the metadata as you see fit. The field `type` should either be
"page" or "post", depending on what kind of page you want to create.  
If you choose create pages manually, it is best to copy the metadata from an existing file and adjust it, in order to
ensure correct formatting.


#### Serving your pages locally with Hugo

To serve your pages locally, execute `hugo server` in your terminal. Hugo will build the pages and spin up a local
server so you can view the pages. The terminal output will tell you under which address you can view the pages: For now
it is [http://localhost:1313/](http://localhost:1313/), though this might change in the future. Simply open this page in
your web browser.

The pages will be served as long as you don't close the terminal window and don't interrupt the process (with 
`Ctrl/Cmd + C`). Hugo will automatically detect any changes you make to the local files, re-build the pages when you
save and refresh your browser. You can therefor simply work on the files while having the browser window open, and all
changes you made will show up whenever you save your progress.


### Markdown

Markdown is a light-weight markup language for encoding text formatting information in an easy-to-remember and
easy-to-read manner. It is very commonly used in the context of software development, so you will see it all over the
place on GitHub. But it is by no means specific for tech documentations - it is very well suited for note-taking and
formatting of non-print texts in all fields.

The markdown syntax is easy to learn, and there are many cheat sheets all over the internet, e.g. 
[here](https://www.markdownguide.org/cheat-sheet/), 
[here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or 
[here](https://www.freecodecamp.org/news/markdown-cheatsheet/). The most important elements are as follows:  
Text renders as text. A single line break is not rendered at all. Double line break starts a new paragraph. A soft line
break is created by ending a line with *two* spaces and then adding a single line break. Headers are created by starting
the line with one or more hash (`#`) signs plus a space; the number of hashes indicates the header level. Bullet point
lists are created by starting the line with a hyphen plus a space; numbered lists are created by starting the line with
a digit, a stop and a space.  
Again, check the cheat sheets linked above to see what else you can do.

Text editors like Visual Studio Code offer great markdown support, like syntax highlighting and a live preview of what
the rendered result will look like.


### Any questions...?

If you still have any questions, don't hesitate to ask Balduin or anyone from "team tinkering".
