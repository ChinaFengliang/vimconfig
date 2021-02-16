My vim configuration

<!-- vim-markdown-toc GFM -->

* [安装 Vim:](#安装-vim)
* [配置](#配置)
    * [Install Vundle plugin manager](#install-vundle-plugin-manager)
    * [安装插件](#安装插件)
    * [安装 powerline 字体](#安装-powerline-字体)
    * [suan/vim-instant-markdown](#suanvim-instant-markdown)
* [源码编译](#源码编译)
    * [配置](#配置-1)
    * [安装](#安装)
* [YouCompleteMe](#youcompleteme)
* [参考文献](#参考文献)

<!-- vim-markdown-toc -->

# 安装 Vim:
```bash
$ sudo apt-get install vim
```
# 配置
```bash
$ cd
$ rm -rf .vim .vimrc
$ git clone https://github.com/jarsonfang/vimconfig.git
$ ln -s vimconfig/vim .vim
$ ln -s vimconfig/vimrc .vimrc
```
## Install Vundle plugin manager
```bash
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
## 安装插件

Launch vim and run`:PluginInstall`command or run `vim +PluginInstall +qall` from
command line directly. After done that, please go to [here](https://github.com/Valloric/YouCompleteMe) to see more about the
installation of YouCompleteMe plugin.

## 安装 powerline 字体
```bash
$ git clone https://github.com/powerline/fonts.git
$ cd fonts && ./install.sh
```
after powerline fonts installed, configure the terminal to use one of the
powerline fonts. 作者认为*Source Code Pro for Powerline Medium*的12号字体
比较舒服。

## suan/vim-instant-markdown
```bash
$ sudo apt-get install xdg-utils curl nodejs-legacy npm
$ sudo npm -g install instant-markdown-d
```
# 源码编译
```
$ git clone https://github.com/vim/vim.git
```
## 配置

在vim的help文档中, 提到`当同时支持Python 2和Python 3时，必须动态加载它们。在
Linux / Unix系统上执行此操作并导入global symbols时，这会导致使用第二个Python版本
时发生崩溃。 所以要么加载global symbols只激活一个Python版本，要么不导入全局符号。
这会导致Python导入vim提供的全局符号的相关库的import出错。` 因此，我们仅编译支持
python 2 或 python 3功能。

支持Python 2配置如下：
```
$ ./configure --with-features=huge \
            --enable-multibyte \
            --enable-rubyinterp=yes \
            --enable-pythoninterp=yes \
            --with-python-config-dir=/usr/lib/python2.7/config-x86_64-linux-gnu \
            --enable-perlinterp=yes \
            --enable-luainterp=yes \
            --enable-cscope \
            --prefix=/usr/local
```
支持Python 3配置如下：
```
$ ./configure --with-features=huge \
            --enable-multibyte \
            --enable-rubyinterp=yes \
            --enable-python3interp=yes \
            --with-python3-config-dir=/usr/lib/python3.6/config-3.6m-x86_64-linux-gnu \
            --enable-perlinterp=yes \
            --enable-luainterp=yes \
            --enable-cscope \
            --prefix=/usr/local
```
## 安装
```
$ make VIMRUNTIMEDIR=/usr/local/share/vim/vim81
$ make install
```
# YouCompleteMe

YouCompleteMe 是一款非常强大的自动补全功能插件。该插件功能依赖python2或python3的
支持，否则将会报错。

# 参考文献

1. http://easwy.com/blog/archives/advanced-vim-skills-catalog/
2. http://blog.csdn.net/wooin/article/details/1858917
3. http://blog.csdn.net/wooin/article/details/2004470
4. http://www.cnblogs.com/zhongcq/p/3642794.html
5. http://blog.csdn.net/fivedoumi/article/details/50594348
