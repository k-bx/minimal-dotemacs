# Minimal dotemacs

This repository contains some minimal configuration that I would use
on a linux server which I use for programming when tramp doesn't work
well enough. It enabled generic things like Cask, Projectile,
Flycheck, and also some more specific like Haskell Mode, Intero etc.

This repository is expected to be cloned or copy-pasted on server to
get "good enough" comfort for working as quickly as possible.

## Installation

```
# 1. Clone the repo
https://github.com/k-bx/minimal-dotemacs.git
# 2. Link `.emacs` and Caskfile
ln -s $(pwd)/minimal-dotemacs/dotemacs.el $HOME/.emacs
mkdir -p $HOME/.emacs.d
ln -s $(pwd)/minimal-dotemacs/Cask $HOME/.emacs.d/Cask
```
