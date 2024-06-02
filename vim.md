# Substitutions 
## From command mode
- `:%s/old_string/new_string/gic`
    - The `s` refers to the `sed` command.
    - It substitutes the first occurrence of `old_str` with `new_str`.
    - The `g` flag at the end makes it global, so such substitutions happen for the entire line.
    - Writing `%s` instead of simply `s` makes these substitutions throughout the whole file.
    - You can specify a set range be prepending the `s` with line numbers, e.g. `:5,10s/...` 
    - If you want to be prompted with a confirmation for each replacement, you can include an extra `c` floag at the end for "confirm".
    - There also exists an `i` flag to make things case-insensitive
    - If you want to enforce the replaced string to be a stand-alone variable name and not a substring, you can enforce word boundaries using `\b`

# Terminal window
  - `:term`
    - Splits the current window in two, producing a terminal window within vim.

# Splitting windows
  - `<C-w>+s`              causes a window split vertically.
  - `<C-w>+c`              closes current window
  - `<C-w>+{hjkl}`         allows you to jump from the current window left, up, down and right, respectively.
  - `:res +/- n`           Resizes the current window integer `n` amount

# Finding files
## Command mode
With `set path+=**` written in your .vimrc, the folder from which you opened your vim session is set as root of a new tree, and having `**` appended to the current path allows for the `:find` command to seach amongst all the leaves. Thus typing `:find filename` allows you to jump directly to a file if it appears somewhere in the tree.

With `set wildmenu` written in your .vimrc, regular expressions such as the `*` wildcard can be used in the `:find` command to browse on partial matches. Thus, writing something like `:find *.py` and pressing `<tab>` instead of `<CR>` allows you to sift through all files matching said pattern.
    
## NERDTree
With NERDTree installed, and `nnoremap [bind] :NERDTreeToggle<CR>` filled out in your .vimrc, hitting the bind opens up a side menu like in any modern IDE holding files of the current directory. This menu can be navigated using regular normal mode commands, and files can be opened using `<CR>` or opened as tabs using `t`.

  - If opened as a tab, you can swap from one tab to the next using <g-t>.

