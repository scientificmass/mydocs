---
layout: default
title: Linux CLI
nav_order: 98
---

## Clear cache on Arch

### Remove cached packages that are not currently installed:
```console
sudo pacman -Sc 
```

### Remove all the package from the cache, including those that are installed:

```
sudo pacman -Scc 
```
## Orphan packages
### Showing the orphan packages
```
sudo pacman -Qtdq 
```
### Remove unused packages (orphans)
```
sudo pacman -Rns $(pacman -Qtdq) 

```
