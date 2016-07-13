# vimsetup
Uniform vim setup across machines


This git includes instructions on setting up VIM environment on new linux / OS-X machines.

## 1. Install pathogen
-------
https://github.com/tpope/vim-pathogen

```bash
mkdir -p ~/.vim/autoload ~/.vim/bundle && \
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
```

Add this at the top of your .vimrc
```
" Pathogen
filetype off " Pathogen needs to run before plugin indent on
call pathogen#infect()
call pathogen#helptags() " generate helptags for everything in 'runtimepath'
filetype plugin indent on
```

## 2. Fortran support
---------

Add the following to .vimrc

```bash
"Fortran related
let fortran_free_source=1
```

## 3. Colorscheme - molokai
-----------

https://github.com/tomasr/molokai
```bash
> cd bundle
> git clone https://github.com/tomasr/molokai.git
```

Add the following to your .vimrc
```bash
"Molokai
if &t_Co >=256 || has("gui_running")
    colorscheme molokai
endif
```

## 4. Syntax highlighting
------
Add the following to your .vimrc
```bash
"syntax
if &t_Co > 2 || has("gui_running")
    syntax on
endif
```

## 5. Python-friendly settings
------
Add the following to your .vimrc
```bash
"Python settings
set nowrap
set autoindent
set tabstop=8
set shiftwidth=4
set softtabstop=4
set expandtab
```

### 6. General useful settings
----
Add the following to your .vimrc

```bash
set pastetoggle=<F2>
set modeline

set guifont=Menlo\ Regular:h14
set ruler
set showmode
set cursorline
hi cursorline guibg=#333333
hi CursorColumn guibg=#333333
set wrap
set ignorecase
set smartcase

set foldmethod=indent
set foldlevel=99
```
