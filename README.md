# linux-config
Speedup new machine setup for bash/python/vim productivity.

## Debian/Ubuntu prerequisites
Install development packages needed by other installers.

```
sudo apt-get install build-essential cmake python3-dev
```

## Bash

```
cp bash_aliases ~/.bash_aliases
```

## Python

### Install pyenv
```
curl https://pyenv.run | bash

# Load pyenv automatically by adding
# the following to ~/.bashrc:

export PATH="/home/syrus/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

## Vim
If needed, you can compile vim from source to ensure python support is included.
```
cp vimrc ~/.vimrc
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Edit your local .vimrc to make any necessary changes such as disabling heavy plugins if on a limited platform such as a Raspberry Pi. Then run vim and execute :PluginInstall to install extensions.

```
$ cd ~/.vim/bundle/YouCompleteMe
$ python3 install.py --all
```
