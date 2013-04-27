# Vim Configuration

This is a fork of the Case Commons' MacVim configuration repository with a few
small additions, notably, the railscasts color theme, keyboard mappings, git
gutter hints and the Command-T plugin with instructions.

    NOTE: You should be using 'brew' for installing various tools, 'rvm' for managing versions 
    of ruby, and you should have XCode installed.

# To Install

(Re)move ~/.vim and ~/.vimrc if you have them already, and run:

    git clone git@github.com:abkonsta/cc-vim-config.git ~/.vim
    cd ~/.vim
    git submodule update --init
    ln -s ~/.vim/vimrc ~/.vimrc
    ln -s ~/.vim/ackrc ~/.ackrc

To make Command-T work, after completing the steps above:

    cd ~/.vim/bundle/command-t/ruby/command-t
    rvm use system
    ruby extconf.rb
    make

If you do not use RVM, you do not need to tell it to use the system ruby.
If you do not have XCode installed, you won't be able to compile the c program.
You can download XCode from Apple's app store. 

To get "Find in project" like functionality from Ack, install ack:

    brew install ack

# Installing and using ctags with Ruby

The 'ctags' binary in /usr/bin that comes with OS X does not support the -R 
option, among other things. Don't use it, install a different one with brew:

    brew install ctags

If you are using rvm, you will be able to generate ctags for your ruby/rails
project (and the current rvm gemset!) using <leader>rt, which is ',rt'.

# ctags key mapping

    Command-]  -  go to definition
    Command-[  -  go to "next tag"
    Ctrl-T     -  go back up the tag stack

For more information, use ':help tagsrch'. All the keybindings should be defined
in ~/.vim/init/keybindings.vim.

# crash course on macvim key bindings

    Command-Shift-N    -  fuzzy search by file name
    :vs or ,v          -  split screen vertically
    :sp                -  split screen horizontally
    :A                 -  toggle between the model and its rspec
    Control-W + arrows -  move buffer focus in the direction of the arrow
    ,b                 -  list previously opened files in all buffers
    \                  -  view the list of files in project (NerdTree)

# Note to iTerm users

For terminal mode vim, use railscasts-iterm color scheme and set your default 
iTerm profile to have dark background color. You can use the shell script 
included in this repository to create a nice pastel-colored profile with dark 
background. *Make sure you completely close iTerm before running the script.*

    cd ~/.vim/iterm
    . ./iterm_profile.sh

The profile script was adapted from http://kpumuk.info.
Turn off transparent background (Command+U), it's annoying.

# Updating

As long as your checkout is kept clean, you can easily update, rebase your local
changes and update submodules with:

    cd ~/.vim && git pull --rebase ; git submodule update ; cd -

