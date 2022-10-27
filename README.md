# bit banger
A short git tutorial for bit bangers and git kangers


## Starting out
So, you want to build a rom, but you don't know git...

<insert stuff about creating a git account, ssh keys, pgp keys>


### git clone
If you are pulling in someone else's repo, this is the place to start.
```
git clone https://github.com/gee-one/bit_banger.git
cd bit_banger
ls
```
You should see the cloned files.


```
git status
git log
```
Now, you should see a clean status and the commit history.

<insert some stuff to explain how commits, authors, and branches work.  keep it simple>

### git init
If you are creating your own repo from scratch, this is a good first step.  Skip this if you used git clone above.

This tells git that you want to create a git repo.

```
mkdir my_rom
cd my_rom
git init .
```

## so now what....  how to work with and manipulate your repo

### git status
```
git status
```
This will show you what is happening in your repo.


### git diff
```
git diff
```
This will show you any uncommited changes, or the last change that was committed if the repo is clean.


### git add/git commit

make some changes to files, or even create new files and folder.  you know do some coding stuffs.

To tell git to track the files, we use git add
```
git add .
```
You can also name individual files, if you only want to add specific ones

```
git rm <files or .>
```
This will tell git that you want to untrack files.  It doesn't delete the file, git just stops tracking it as part of the repo.


Then tell git that you want to add the changes to your repo

```
git commit -a
```
The -a flag tells git to add all tracked files.  You can also specify individual files, if that is all you want to add to one commit.


### git remote
This is how git keeps track of different sources.  You can have several remote repos.
```
git remote -v
```
This will show you the name of the remote and it's URL.  Now we know where to push our files.

### git push
This is how you add your files to the remote repo.

```
git push github main
```
github is the name from `git remote -v` and main is the branch in the repo.


```
git status
```
to verify that we are in sync with the remote repo


### git fetch/cherry-pick
Let's say there is a commit that you want to pull a commit... maybe this one...

```
git fetch https://github.com/gee-one/bit_banger d7dd8adcc2fade7b3a05480239e7e3e6a9cdf634
git cherry-pick FETCH_HEAD
git log
```
did it work?
```
git diff
```
