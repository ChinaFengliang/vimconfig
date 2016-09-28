My vim configuration

## Install Vim:

```bash
$ sudo apt-get install vim
```

## Install configuration

```bash
$ cd
$ rm -rf .vim .vimrc
$ mkdir -p etc
$ git clone https://github.com/ChinaFengliang/vimconfig.git etc/vim
$ ln -s etc/vim/plugin .vim
$ ln -s etc/vim/vimrc .vimrc
```

## Install Vundle plugin manager

```bash
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

## Install other plugins

Launch vim and run`:PluginInstall`command or run `vim +PluginInstall +qall` from command line directly. After done that, please go to <https://github.com/Valloric/YouCompleteMe> to see more about the installation of YouCompleteMe plugin.

## Install powerline fonts

```bash
$ git clone https://github.com/powerline/fonts.git
$ cd fonts && ./install.sh
```

after powerline fonts installed, configure the terminal to use one of the powerline fonts.

## Install dependencies for `suan/vim-instant-markdown`

```bash
$ sudo apt-get install xdg-utils curl nodejs-legacy npm
$ sudo npm -g install instant-markdown-d
```

## References

1. http://easwy.com/blog/archives/advanced-vim-skills-catalog/
2. http://blog.csdn.net/wooin/article/details/1858917
3. http://blog.csdn.net/wooin/article/details/2004470
4. http://www.cnblogs.com/zhongcq/p/3642794.html
5. http://blog.csdn.net/fivedoumi/article/details/50594348
