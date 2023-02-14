---
layout: default
title: git tutorials 
parent: Github
---
### Git exclude folder
Put this .gitignore into the folder, then git add .gitignore.
```
*
!.gitignore
```
### You can't commit empty folders in git.
If you want it to show up, you need to put something in it, even just an empty file. For example, add an empty file called .gitkeep to the folder you want to keep, then in your .gitignore file write:
```
# exclude everything
somefolder/*

# exception to the rule
!somefolder/.gitkeep 
```
### Add file anyways
```
git add -f file
```
### Git does not recurse into ignored directories [Source](https://stackoverflow.com/questions/69102876/different-behavior-for-two-whitelisted-nested-directories-in-my-gitignore-file) 
The problem is that once a directory is excluded by the .gitignore logic, Git will not recurse into it to find things inside it that might not be ignored. This is an important optimization to keep Git fast.

With `/*` in there, `.config` is ignored, so Git never even notices that `.config/i3/` exists. The solution is to add another line to say "don't ignore `.config`", so that Git will recurse into it:
```
# ignore all of home dir
/*
# exclude .config folder
!.config
# ignore .config subdirs
.config/*
# exlude i3 folder in .config
!.config/i3/
```
Now, you probably still wanted `.config/something-else` ignored, so you need one more line to do that.
