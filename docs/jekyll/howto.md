---
layout: default
title: HowTo
parent: Jekyll
---
## Sources
- [Jekyll Docs](https://jekyllrb.com/docs/)


## Install all prerequisites.
- Ruby version 2.5.0 or higher
- RubyGems
- GCC and Make

## Ubuntu
```
sudo apt-get install ruby-full build-essential zlib1g-dev
```
- Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path:
```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
- Finally, install Jekyll and Bundler:
```
gem install jekyll bundler
```

## Arch (+ same as on unbuntu)
```
sudo pacman -S ruby base-devel
```
## Install the jekyll and bundler gems.
```
gem install jekyll bundler
```
## Create a new Jekyll site at ./myblog.
```
jekyll new myblog
```
## Change into your new directory.
```
cd myblog
```
## Build the site and make it available on a local server.
```
bundle exec jekyll serve
```
## Browse to
```
http://localhost:4000
```
## Start with livereload to update during development
```
bundle exec jekyll serve --livereload
```
