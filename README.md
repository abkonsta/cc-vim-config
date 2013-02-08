# Vim Configuration

    This is a fork of the Case Commons' MacVim configuration repository
    with a few small additions, notably, the railscasts color theme and
    keyboard mapping to support Cmd+Shit+N for invoking the Command-T
    vim plugin.

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

These instructions assume that you use RVM and that you have XCode installed.
If you do not use RVM, you do not need to tell it to use the system ruby.
You can download XCode from Apple's app store. 

# Updating

As long as your checkout is kept clean, you can easily update, rebase your local changes and update submodules with:

    cd ~/.vim && git pull --rebase ; git submodule update ; cd -
