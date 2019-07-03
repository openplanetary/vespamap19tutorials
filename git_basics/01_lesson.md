# What is Git

- - -
**Note:**
In this tutorial, _italic_ words will oftenly be used on jargons of the Git
framework. While `typewrite` format is used to highlight commands, or
command-based expressions.
- - -

[Git](https://git-scm.com) is a software control manager (SCM),
which stands for a system that
manages modifications -- or _version_ -- of files base.
Git is popularly used to keep track of code bases and structure the development
and release of software, hence the popular term _version control system_ to
describe.
But in reality Git can be used to track modifications of any kind of file
content.

## Distributed

The way a SCM system works in general is based on a central server holding
the code base where clients will download/upload (_sync_) modifications
following a given workflow.
Git breaks this workflow in many stages and dissolves the figure of the
central server to build a loosely connected network of mirrors.
In fact, Git is distributed by definition: it doesn't really consider the
existence of a central server to work, the tracking of a repository's
content can exist completely offline in a user's personal computer alone.

## Branches

An expression very common to the Git environment is _branches_.
Here is an abstraction of the _branches_ scenario:

<img src='https://git-scm.com/images/about/branches@2x.png' alt='Git branches' width=500px>

Branches are versions of your repository.
Every repository has a _master_<sup>^</sup> branch, from which new branches
can be created. Branches allow developers to edit part of the code base
-- say you want to test a new feature for your software -- without disturbing
the code in the branches (for instance, `master`).
One is free, an safe, to switch _branches_.

Suppose the feature you are implementing/testing in the new _branch_
happened not to be feasible and you decide to not keep its implementation:
at this point all you have to do is to delete it and _checkout_
back to the master branch.
On the other hand -- another day, another feature -- you decide that the new
code implementation is good and should be part of your software: you will
then _merge_ the new branch into the master branch; and then you can delete
the (now old) branch.


## Structure of a repository

The big picture of a Git ecosystem is illustrated below:
![Git structure](./images/git_structure.png)

This figure summarizes the basic workflow and persived structure of a Git repository.

At the very top we see references of a _Local_ area and a _Remote_ area, those
make reference to what happen in your _local_ computer<sup>*</sup> and _remote_
server<sup>*</sup>.

The _local_ repository is of our primary interest here.
We notice _Local_ is split in three
layers. The _working directory_ is our visible set of files, which we edit and
interact with; Git knows which and what in the files it is tracking has been
changed here, but it is controling those modifications at this layer.

To make Git "register" the modifications we have done we have to `git add`
those files/modifications, at this point the modifications go to the repo's
_staging area_, also called the _index_. One can "add" as much modifications
as necessary to the _staging area_.

Eventually the user will `git commit` the "proposed" modifications to what is
here called _local repo_. **It is a good practice to _add_ and _commit_ oftenly
the modifications.**

If one is working with a _remote repo_ (_e.g._, Github), `git push` will push
the previous _commit(s)_ to the _remote repo_.

In case the user works from multiple workstations (_e.g._, a laptop and a
desktop) or multiple users collaborate in the same code base
(_i.e._, repository), `git fetch` will fetch the current state of the _remote repo_
to your `local repo`, and `git merge` will bring it to your _working directory_,
the place where you can effectivelly edit the current repository content.

It is very common to use `git pull` instead of `git fetch` + `git merge`.

`git checkout` is the command to manipulate modifications in the
_working directory_. You will use `git checkout` whenever you want to change
_branch_ or throw out modifications done to a file (before _staging_ it).

- - -
<sup>^</sup> A `master` branch by default is more of a convention, Git itself
does not hardcode the existence of `master` but it is a default.

<sup>*</sup> To be very specific, _local_ and _remote_ repositories can exist
in the very same machine, Git doesn't really care where the repositories are or
how they connect to each other.
