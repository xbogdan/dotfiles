## VIM Configuration

* Compatible with [Vim](http://www.vim.org/) and [Neovim](https://neovim.io/).
* Layout compatible for `Neovim` but easily linkable for `Vim`.
* All `Neovim` specific plugins, settings, key mappings etc. are isolated with
  `has('nvim')` conditionals.
* Recommended environment includes [iTerm nightly](https://www.iterm2.com/downloads/nightly) and [tmux](https://tmux.github.io/).
* Plugins managed by [vim-plug](https://github.com/junegunn/vim-plug).
* Primary programming languages supported: `Python`, `Rust`, `Go`, `Clojure` and `Common Lisp`
* Mnemonic keyboard shortcuts. E.g. file based actions under `<Leader>f` and
  buffer based shortcuts are under `<Leader>b`.
* Leader key is `space`.
* Local leader is `\`.

### Installation

#### MacOS

* Install `Neovim` and `Vim` (i prefer HEAD for both).
        
        brew install neovim --HEAD
        brew install vim --with-luajit --with-override-system-vi --HEAD

* For Neovim it is recommended to use separated virtual python environments for
  editor's own needs. For any shell these virtual environments must be located under `~/.virtualenvs/`.

        virtualenv neovim2
        pip install neovim

        virtualenv --python=python3 neovim3
        pip3 install neovim

* Install ruby plugins
        
        [sudo] gem install neovim

* Clone repository to any place you prefer.

        git clone https://github.com/xbogdan/dotfiles 

* Create symbolic links for both editors.

        cd $HOME
        cd .config
        ln -s /path/to/dotfiles/nvim .

        cd $HOME
        ln -s /path/to/dotfiles/nvim .vim
        ln -s /path/to/dotfiles/nvim/init.vim .vimrc

* Create necessary directories.

        cd $HOME
        mkdir .nvimtmp

* First run will give errors. Ignore them.

        nvim
        vim

* For each editor execute `:PlugInstall` command.

### Plugins List

Check [plugins.vim](https://github.com/zekzekus/dotfiles/blob/master/nvim/plugins.vim) for all plugins and [keybindings.vim](https://github.com/zekzekus/dotfiles/blob/master/nvim/keybindings.vim) for all custom
keybindings.

## TMUX Configuration

### Mac OS X

- First install Homebrew

        /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

- Next, install the `tmux` and `reattach-to-user-namespace` packages using Homebrew

        brew install tmux
        brew install reattach-to-user-namespace

- Create a symbolic link to `dotfiles/tmux/tmux.conf`

        ln -s /path/to/repo/dotfiles/tmux/tmux.conf ~/.tmux.conf

- ###### (Optional) Change the shell 
    - Open `~/.tmux.conf` in your favourite editor and edit the `MYSHELL` and `MYSHELL_PATH`.

            ...
            3 # SHELL choice (zsh | fish)
            4 MYSHELL=zsh
            5 MYSHELL_PATH=/usr/local/bin/zsh
            ...

- Run tmux

    `~$ tmux`

