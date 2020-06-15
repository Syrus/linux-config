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

# to build python from source
sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev python-openssl git

# install python
env PYTHON_CONFIGURE_OPTS="--enable-shared" pyenv install 3.8.3
```

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
If this is a desktop machine, you may install vim-gnome instead of vim-nox.

```
sudo apt-get vim-nox
cp vimrc ~/.vimrc
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Edit your local .vimrc to make any necessary changes such as disabling heavy plugins if on a limited platform such as a Raspberry Pi. Then run vim and execute :PluginInstall to install extensions.

```
cd ~/.vim/bundle/YouCompleteMe
python3 install.py --all
```
