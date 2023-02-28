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

### For a quick installation of omv-extras, on Openmediavault, run the following command as root:
```
sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```
[Github](https://github.com/OpenMediaVault-Plugin-Developers/installScript/)

### Deployment
Before deploying the container, make sure that the volume host directories exist. You can copy/paste the information from Portainer and create the directories if needed.

Instead of using the command line, you can of course also create the directories using your favorite file manager.

mkdir -p /volume1/docker/sonarr/config
mkdir -p /volume1/docker/sonarr/tv
mkdir -p /volume1/docker/sonarr/downloads