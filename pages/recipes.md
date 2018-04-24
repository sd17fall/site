---
title: Recipes
permalink: resources/recipes/
redirect_from: resources/git/
---

{% include toc %}

This page is a companion to the [Resources]({% link pages/resources.md %}) page.

## Python Recipes

### Install PyGame

Linux:

```bash
$ apt-get build-dep python-pygame
$ apt-get install mercurial python-dev python-numpy ffmpeg libsdl-image1.2-dev libsdl-mixer1.2-dev libsdl-ttf2.0-dev libsmpeg-dev libsdl1.2-dev libportmidi-dev libswscale-dev libavformat-dev libavcodec-dev
$ pip install pygame
```

### Fix "NameError: name 'math' is not defined"

Fix "NameError: name 'math' is not defined" (or another module):

```python
import math
```

### Fix "RecursionError: maximum recursion depth exceeded"

Your recursive function is either missing a base case, or is somehow not executing it (for example, it is calling itself with the same arguments that it was called with – TBD illustrated in the Recursion notes).

### Using doctest

Run all the doctests in a module (file, script): `doctest.testmod()`

Run the doctests with verbose output: `doctest.testmod(verbose=True)`

Test a single function: `doctest.run_docstring_examples(get_complement, globals())`

Test a single function with verbose output: `doctest.run_docstring_examples(get_complement, globals(), verbose=True)`

### Working with Turtles

```python
import turtle

t = turtle.Turtle()
# …
turtle.mainloop()
```

### Re-run program when file changes

1. [Install nodejs](https://nodejs.org/en/download/)
2. [`npm install onchange`](npm install onchange)
3. Run your program e.g. `onchange '*.py' -- python script.py`

Previous semester have also used [entr](http://entrproject.org) and [pytest-watch](https://github.com/joeyespo/pytest-watch) for this. I also tried [when-changed](https://github.com/joh/when-changed).

## Pygame recipes

### Set window position

```python
os.environ['SDL_VIDEO_WINDOW_POS'] = "0,0"
```

## Atom Recipes

### Enable autosave

Enable autosave, to avoid ever seeing the workflow bug that the code you're running or committing doesn't include your latest change(s):

1. Select Atom Preferences (<kbd>cmd+,</kbd>)
2. Click "Packages"
3. Find the "autosave" package
4. Click "Settings"
5. Enable "Enabled"

### Use multiple cursors

Use [multiple cursors and selections](http://flight-manual.atom.io/using-atom/sections/editing-and-deleting-text/#multiple-cursors-and-selections) to edit several places at once.

### Make Hydrogen work with Anaconda
Make the Hydrogen plugin work with Anaconda Python:

* The easy way: always launch atom by running `atom` in the Anaconda Command Prompt.

## Git Recipes

### Working with Reading Journals

This material is now on the [Reading Journal]({% link pages/reading-journal.md %}) page.

### `.gitignore`: Ignoring Files

* [GitHub documentation](https://help.github.com/articles/ignoring-files/)
* [Tutorial from Atlassian](https://www.atlassian.com/git/tutorials/gitignore)
* [`.gitignore` templates](https://www.gitignore.io)

### Get stuff from my computer to GitHub

```bash
$ git add <filename>
$ git commit -m "<commit-message>"
$ git push
```

You can alternatively use `git commit -am '<commit-message>'` to both add all
of the files in your folder and put a message on them, all in one command!

If you forget to include `-m` in your commit, git will open a text-editor called
vim so that you can enter a commit message there. To write your commit message
in vim, first press “i”, then write your message, then type <kbd>:wq</kbd> for write-
quit. Alternatively, if you just want to escape from vim's interface without
saving a message, just enter “:q” for quit.

### Pull changes from GitHub

```bash
$ git pull
```

-or-

```bash
$ git pull origin master
```

If you get merging errors telling you that you need to merge or 'stash' before
you can pull, see the 'stashing' section below. Also, a quick note on pulling,
what pulling means is that you're taking the code that others have pushed to
your repository and matching what you have on your computer with that, so it
incorporates their changes.

### How to stash (and what is stashing?)

```bash
$ git stash
```

Stashing stores the copy of your current version of the repository on your
computer, so you can keep that copy there before you pull changes that others
have made. Often, you'll be prompted to stash before pulling or merging with
others. Now that you've stashed, how do you get your stuff back? You'll
probably do the following:

```bash
$ git stash
$ git pull
$ git stash pop
```

Git stash will store your changes locally, git pull will download the changes
other have made to the repository, and git stash pop puts the changes that you
made locally that conflict directly in the code. If there's anything to merge,
do it in the file and then commit and push your changes.

### Fix a Git detached head

`$ git checkout master`

If this doesn't work, try:

`$ git checkout origin/master`

### What is branching on Git?

Branches on Git are very similar to branches on trees. The tree trunk is
represented as the `master` branch and the branches that come off of the
master branch you can name whatever you want. These branches will start at
whatever state master was at the time you made the branch. The master branch
can continue changing independently of the branch that you created. You can
combine the changes that you make in separate branches by 'merging' them
together. For more on merging, look at the sections that will follow. Also,
you can view all of the branches in your repository by doing:

`$ git branch -a`

And you can tell what branch you're on by doing the command:

`$ git branch`

### Make a new branch

`$ git fetch origin`

`$ git checkout -b <your-branch-name> origin/master`

This branch will exist on your computer, in order to push it to git and have
it be visible by others, you'll have to push your local branch to be a remote
branch (see below)

### Push your local branch to be a remote branch

`$ git push -u origin <your-branch-name>`

### Check out a branch

'Checking out' a branch is when you pull another person's branch (or teleport
to another branch), you do it by doing:

```bash
$ git fetch origin
$ git checkout <branch-name>
```

### Resolve merge conflicts

See [Resolving a Merge Conflict Using the Command Line
](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/) on GitHub.

### Merge one branch into another

Let's say that you've been working on a branch called `dev` and you have also
been modifying the `master` branch. You want to merge your changes in the
`master` branch into the `dev` branch, so that your `dev` branch is up to
date. What you want to do is first get into the `dev` branch, then:

```bash
$ git fetch origin
$ git merge origin/master
```

If you have any conflicts, deal with them, commit and push your changes, and
you're good to go!
