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

