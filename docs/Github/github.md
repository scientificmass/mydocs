---
layout: default
title: Github
nav_order: 6
has_children: true
permalink: docs/github
---

# Utilities
{: .no_toc }

### Setting up a global .gitignore file [Source](https://sebastiandedeyne.com/setting-up-a-global-gitignore-file/) 
Reviewing pull requests, I often see contributors sneakily adding editor configuration to the repository’s .gitignore file.
```
  composer.lock
  package.lock
+ .vscode
```
If everyone would commit their environment-specific .gitignore rules, we’d have a long list to maintain! My repository doesn’t care about your editor configuration.

There’s a better solution to this: a personal, global .gitignore file for all your repositories. Here’s how you can set one up.

Global .gitignore 101
First, create a .gitignore file for your global rules. Most people keep this in their home directory.
```
touch ~/.gitignore
```
Next, open it with your text editor of choice and add whatever files and folders you always want to ignore. Here’s what my global configuration looks like:
```
.DS_Store
.vscode
```
You’ll probably have at least two entries in your global .gitignore: one for operating system-specific files, and one for editor-specific files.

I’m a Mac user, so I need to ignore .DS_Store files created by macOS. I use Visual Studio Code, so I need to ignore .vscode folders.

If I were a Windows user with PHPStorm as my primary editor, my .gitignore file would probably look like this:
```
Thumbs.db
.idea
```
Finally, configure git to use our newly created ~/.gitignore file.
```
git config --global core.excludesfile ~/.gitignore
```
If you’re a Windows user, you’ll need to format the path differently.
```
git config --global core.excludesfile %USERPROFILE%\.gitignore
```
That’s it, no more pesky editor configuration in your commits!


### Open pdf in new window on a github page [Source](https://stackoverflow.com/questions/30745981/opening-pdf-in-a-browser-with-github-pages)

Suppose your personal website is hosted in a Github page as follows:

https://username.github.io
The repository should be name as username.github.io. If you have a pdf file named document.pdf and you place it in the directory folder then you should be able to open it directly in the browser through the following link:

https://username.github.io/folder/document.pdf
To allow the user to open the pdf in a new window in the browser, you may use the following HTML, where "PDF" points to the link:

<a href="https://username.github.io/folder/document.pdf" target="_blank">PDF.</a>


**Embed**

It's very easy to display Pdf in browser from Github static page, for that you need approach following process,

Make the static website/repository using your Github username, for example, if the username is sumanbogati then repository would be sumanbogati.github.io
Put the desired pdf in that repository
Now locate the Url of Pdf wherever you want
For example, to display pdf in Html web page

<embed src="https://sumanbogati.github.io/sample.pdf" type="application/pdf" />
This is an instant demo.