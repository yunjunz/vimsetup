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

## 2. Colorscheme - molokai
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

## 3. Syntax highlighting
------
Install syntastic from https://github.com/scrooloose/syntastic
```bash
> cd bundle
> git clone https://github.com/scrooloose/syntastic.git
```

Add the following to your .vimrc
```bash
"syntax
if &t_Co > 2 || has("gui_running")
    syntax on
endif

"Fortran related
let fortran_free_source=1

"Syntastic
let g:syntastic_enable_signs=1
let g:syntastic_check_on_open=1
let g:syntastic_fortran_flags='-ffixed-line-length-none'
let g:yankring_history_dir = '$HOME/.vim'

```

## 4. Python-friendly settings
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

You can define a function to autofix tabs in python files:
```bash
"Esc-py to retab the file
function! Ptab()
    :set expandtab
    :retab
endfunction
map py :call Ptab() <CR>
```

### 4. General useful settings
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
