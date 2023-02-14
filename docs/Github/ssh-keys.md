---
layout: default
title: Using multiple ssh keys
parent: Github
---
### Check git config
```
git config --list
```

### Set the name and email for this repo
git config user.name "Name"
git config user.email "email@gmail.com"

### For setting it globally add --global to the command
```
--global
```
### Edit ~/.ssh/config
```
Host main
  Hostname github.com
  IdentityFile ~/.ssh/github
  IdentitiesOnly yes

Host old
  Hostname github.com
  IdentityFile ~/.ssh/id_rsa
  IdentitiesOnly yes
```
### Remove the wrong remote repo
```
git remote remove origin
```
```
git remote add origin git@main:username/repository.git
```
### Format of remote add >>
```
git remote add origin git@gh_sc:scientificmass/dotfiles.git
```
