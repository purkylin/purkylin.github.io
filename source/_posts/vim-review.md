---
title: vim编辑器
date: 2018-07-10 11:44:28
tags:
---

## 编辑器
用过很多编辑器，目前终端下用neovim，gui用[oni](https://github.com/onivim/oni), 当然VS Code也是一个不错的选择。oni是基于neovim, 使用node编写的非原生app,内置交互式vim教程，有漂亮的ui，并且集成常用的插件，目前还在快速开发中。
## 经常忘记的命令，包括插件

1. 定位到第一个非空字符 `_`
2. fold

```
set fdm=syntax
```

| command | comment |
|----------|--------|
| zc | close |
| zo | open |
| zf | create |
| zd | delete |

3. plugin

  1. [comment]([GitHub - tpope/vim-commentary: commentary.vim: comment stuff out](https://github.com/tpope/vim-commentary))
    * `[n]gcc`注释当前行
    * `gcap`注释当前段落
    * `gc`visual模式下注释
  2. [unimpaired](https://github.com/tpope/vim-unimpaired)
    * `[ ` or `] `添加空行, 注意后面有空格
    * `[e`or `]e`交换行
  4. [surround](https://github.com/tpope/vim-surround)
    * `cs"'` 用单引号替换双引号
    * `ds"`去除边界

### 我的vimrc
```vim
set mouse=a
set number
set fdm=syntax

set softtabstop=4
set shiftwidth=4
set tabstop=4
set expandtab

let g:python2_host_prog = '/usr/bin/python'
let g:python3_host_prog = '/usr/local/bin/python3'

call plug#begin('~/.local/share/nvim/plugged')
" Plug 'morhetz/gruvbox'
Plug 'roxma/nvim-completion-manager'
Plug 'roxma/nvim-cm-tern', {'do': 'npm install'}
Plug 'trevordmiller/nova-vim'
call plug#end()

" colorscheme gruvbox
colorscheme nova
" set background=dark    " Setting dark mode

set pastetoggle=<F10>

vnoremap  <leader>y  "+y
nnoremap  <leader>yy "+yy
nnoremap  <leader>p "+p
nnoremap  <leader>P "+P

noremap   <leader>source :source $MYVIMRC
noremap   <leader>sudo :w !sudo tee % > /dev/null

```
