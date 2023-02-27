---
layout: default
title: OMV
nav_order: 7
has_children: true
permalink: docs/openmediavault
---
### Upgrade to OMV 6 
[Source](https://forum.openmediavault.org/index.php?thread%2F42340-is-there-a-guide-to-in-place-upgrade%2F&postID=305564#post305564)

Make sure your current install is correct all configs can be deployed by running

```console
sudo omv-salt stage run deploy
```

Get the current install up to date:

```console
sudo omv-upgrade
```

Do the release upgrade by running

```console
sudo omv-release-upgrade
```

If you see an error message from patch which says a patch has alredy been applied, ignore it. (this is the only error to be ignored)

### Docker/portainer error
[Source](https://stackoverflow.com/questions/75489013/docker-not-working-anymore-after-applying-updates-to-openmediavault)
```console
sudo apt-get install apparmor-utils
sudo apt install apparmor-profiles apparmor-profiles-extra
```