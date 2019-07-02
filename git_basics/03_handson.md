# Hands on Git

At this point we should put in practice those basic commands in what is
likely to be our everyday git workflow.

To this hands-on I thought about writing down a simple note, document with
information from the workshop -- but any note/document will do it.
A second suggestion given by Luca is simple and effective to work out
collaborative editing: fill a document template.

For the simple individual exercise follow the `Individual note` section below.

Those willing to edit collaborative follow the instructions in `Collaborative note`
below

For each iteration of our editing (using the text editor of your choice) we
will follow it by:
* `$ git status`
* `$ git add mapping_workshop_2019.txt`
* `$ git status`
* `$ git commit -m "Short informative message"`
* `$ git log`

_That_ is the basic loop you will go through with Git.


## Collaborative note

* Clone this repository:
```bash
$ git clone https://github.com/openplanetary/vespamap19tutorials.git
```

* Go to `vespamap19tutorials/git_basics` and start editing the document
`EDITME.md`

> By the way, feel free to edit _any_ document if you feel like fixing/incrementing some info.

Notice that the collaborative edition needs frequent synchronization with the
remote repo.
To keep your colleagues aware of your local changes you will have to _push_
your commits as often as you understand necessary for people to see it.
On the other hand, you want to be aware of the modifications done by the others
frequent _pulls_ are necessary.

> If the remote repository has new modifications -- since your last _pull_ --
> you will _not_ be able to _push_ your modifications. Which means you need to
> guarantee you local repo has the current state of remote (`git pull`)
> before pushing yours.

The following series of commands will _probably_ give you a smooth ride:
* After editing the `EDITME.md` file:
  * `git add EDITME.md`
  * `git commit -m "short message about your editing"`
  * `git pull`
  * Conflict? Great! Let's handle it, and then `git merge`
  * `git push`


## Individual note

### Init repo

```bash
$ mkdir hands_on_git && cd hands_on_git

$ git init .

$ cat > readme.txt << EOF
# Hands-on Git
This is the start of a better geek-life O.O
EOF

$ git status

$ git add readme.txt

$ git status

$ git commit -m "Init repo ;)"
```


### Create document

Now we create a file called `mapping_workshop_2019.txt` and start filling it
with highlights, information that we learned, are important, or we liked for
some reason.

We may start our note/document with a "skeleton":

> `mapping_workshop_2019.txt`:
```
# Open software/data initiatives

# Status of projects

# Lessons learned

# Food
```

And then:
```bash
$ git add mapping_workshop_2019.txt
$ git commit -m "Create skeleton of mapping note"
```

### Continue editing

Now we add some information:

> `mapping_workshop_2019.txt`:
```
# Open software/data initiatives
* OpenPlanetary
* Aladin
* Topcat

# Status of projects
* VESPA: EPN-what?
* Planmap: Angelo wants a 10-D viewer... Cesium-137 with some LSD may do it

# Lessons learned
* ...LSD is mandatory

# Food
* Pain au chocolat forever
```

And then:
```bash
$ git add mapping_workshop_2019.txt
$ git status
$ git commit -m "Add content to sections"
```

Eventually, if there is a _remote_ repo (e.g., Github) you will:
* `$ git push`
