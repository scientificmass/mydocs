---
layout: default
title: Settings
parent: Neovim
---

# Neovim setup
Arch 
```bash
sudo pacman -S neovim
```
Ubuntu
First install some dependencies:
```bash
sudo apt install software-properties-common -y
```
Import Stable Neovim PPA - Older versions
```bash
sudo add-apt-repository ppa:neovim-ppa/stable -y
```
Import Unstable Neovim PPA - Newer versions
```bash
sudo add-apt-repository ppa:neovim-ppa/unstable -y
```
```bash
sudo apt update
```
```bash
sudo apt install neovim -y
```
## Terminal glyph problem on xfce-terminal
Install Nerd Fonts Fira Code
```bash
yay nerd-fonts-fira-code
```
## Plugin requirements
### [Markdown Preview](https://github.com/iamcco/markdown-preview.nvim) 
#### Install yarn
```bash
yay yarn
```
#### Install Nodejs
```bash
sudo pacman -S nodejs npm
```
#### Install with packer
```lua
-- install without yarn or npm
use({
    "iamcco/markdown-preview.nvim",
    run = function() vim.fn["mkdp#util#install"]() end,
})

use({ "iamcco/markdown-preview.nvim", run = "cd app && npm install", setup = function() vim.g.mkdp_filetypes = { "markdown" } end, ft = { "markdown" }, })
```
#### Manual install
add to `plugins.lua`
```lua
use {'iamcco/markdown-preview.nvim'}
```
and
```bash
cd ~/.local/share/nvim/site/pack/packer/start/
git clone https://github.com/iamcco/markdown-preview.nvim.git
cd markdown-preview.nvim
yarn install
yarn build
```
Packersync breaks it ...
#### This worked on Arch
install npm and yarn and add to config
```bash
use({ "iamcco/markdown-preview.nvim", run = "cd app && npm install", setup = function() vim.g.mkdp_filetypes = { "markdown" } end, ft = { "markdown" }, })
```
in neovim
```lua
:PackerInstall markdown-preview.nvim
 ```
#### Preview in surf browser
```bash
yay surf-git
```
### Latex Preview
#### Texlive for Latex
```bash
sudo pacman -S texlive-core
```
or
```bash
sudo pacman -S texlive-most
```
and
```bash
sudo pacman -S biber
```

#### Zathura for pdf viewing
```bash
sudo pacman -S zathura-pdf-poppler
```
### Python
```bash
sudo pacman -S python
```
pip
```bash
sudo pacman -S python-pip
```
pynvim
```bash
python3 -m pip install --user --upgrade pynvim
```
### Testing startuptime
#### Testing with hyperfine
```bash
hyperfine "nvim --headless +qa"
```
#### Testing with startup
```bash
nvim --startuptime startup.log -c exit && tail -100 startup.log
```
### Language servers
- There has to be certain files in the project`s root folder!
- .git, composer.json, etc.
### Dictionary
- install aspell aspell-en
- install cmp-dictionary
- run following command to get a dictionary file for this plugin (plain text):
> aspell -d en dump master | aspell -l en expand > my.dict