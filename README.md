# Minimal dotemacs

This repository contains some minimal configuration that I would use
on a linux server which I use for programming when tramp doesn't work
well enough. It enabled generic things like Cask, Projectile,
Flycheck, and also some more specific like Haskell Mode, Intero etc.

This repository is expected to be cloned or copy-pasted on server to
get "good enough" comfort for working as quickly as possible.

## Installation

```
# 0. Emacs 25 needed. For old Ubuntu, do
sudo add-apt-repository -y ppa:ubuntu-elisp && sudo apt-get update && sudo apt-get install emacs-snapshot-nox
# 0. Install haskell stack tool
curl -sSL https://get.haskellstack.org/ | sh
# 0. Install some tools. Might need to do `stack setup --resolver nightly` to install latest GHC first
stack install --resolver nightly hasktags hindent
# 1. Clone the repo
git clone https://github.com/k-bx/minimal-dotemacs.git
# 2. Link `.emacs` and Caskfile
rm ~/.emacs
ln -s $(pwd)/minimal-dotemacs/dotemacs.el $HOME/.emacs
rm -rf ~/.emacs.d
ln -s $(pwd)/minimal-dotemacs/dotemacs $HOME/.emacs.d
# 3. Because of the certificate issues, launch emacs via `emacs -q`,
# open `~/.emacs`, eval these:
#     (require 'package)
#     (custom-set-variables ...)
# Then run `M-x package-list-packages` and press `a` for "Always"
# trusting a certificate
# 4. Install cask
curl -fsSL https://raw.githubusercontent.com/cask/cask/master/go | python
# 5. Run cask Install
cd $HOME/.emacs.d
cask install
```
