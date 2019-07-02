# Git basics

A typical workflow in your repository goes like:
1. `git pull` a fresh version from the remote repository;
2. `git branch` a new branch to make your changes;
3. `git checkout` to the new branch;
4. modify one of more files, maybe add/delete some too;
5. `git add` modified/new files;
6. `git commit` what's in the _index_;
7. `git checkout` back to the _master_ branch;
8. `git merge` the "new branch" into master;
9. `git push` back to the _origin_ (remote repo);
10. `git branch --delete` the "new branch".

And that is basically it!

This is a basic though complete and safe workflow. Steps `2, 3, 7, 8, 10` are
not necessary if you don't mind editing the `master` branch directly -- and
you will most probably do that if you don't share your repository -- but I'm
giving you here some (just _some_) guidance to a better experience.


## Everyday commands

* `git-init`: initialize a directory as a repository
```
$ cd new_project
$ git init .
```

* `git-clone`: clone a remote repository
```
$ git clone <existing-project-url>
```

* `git-log`: show the history of a repository
```
$ git log
```

* `git-branch`: manage branches
```
$ git branch --all        # list all branches of repository
$ git branch new_branch   # create branch 'new_branch'
```

* `git checkout`: revert or move working directory
```
$ git checkout new_branch             # go to 'master' branch
$ git checkout -- <modified-file>     # revert modification from <modified-file>
```

* `git-add`: add modifications to staging area
```
$ git add <modified-file>     # add modification to <modified-file> to index
$ git add <new-file>          # add <new-file> to index (stagin area)
```

* `git-diff`: compare differences between files/branches
```
$ git diff master..new_branch   # show differences between master and new_branch
```

* `git-status`: show current state of the repository
```
$ git status    # show current repository's index/working directory status
```

* `git-commit`: commit staged modifications
```
$ git commit -am "a message"    # apply _index_ modifications with "a message" message
```

* `git-merge`: merge branches
```
$ git checkout master     # say we're in 'new_branch', just go back to master
$ git merge new_branch    # apply 'new_branch' state to 'master' branch
```

* `git-tag`: manage repository tags (_aka_ "versions")
```
$ git tag -a "First version" v1.0   # create a 'v1.0' (annotated) tag
$ git tag                           # list repo tags
```
