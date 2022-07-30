First you need to find where your vimrc files lives

`~/.config/nvim/init.vim` are where the config files live for nvim
This is where you can configure vim as you're liking.

To make the configurations of `:set` stick to all vim instances. We need to make sure they are loaded for every vim instance

This is how the final file would look like.
```
" Scrolls automatically when 16 lines are left
set scrolloff=16

set number
set relativenumber

" This is for the tab sapce
set tabstop=4 softtabstop=4
set shiftwidth=4
set expandtab
set smartindent

" This is for the color scheme
colorscheme desert

" Remaps
let mapleader=" "

" Opens project view on the vertical split
nnoremap <leader>pv :Vex<CR>
```

`:so %` to source this `.vimrc` file to reflect changes

`7dd` wiill repeat `dd` 7 times
`Shift v 6 j d`  Select visual line 6 down and delete

`:h options` would list all the possible options for `:set ` commands in vim.

With `:h <SEARCH TERM> ` I can enter `tab` or `Ctrl d` to list all the possible values,
Then `tab` and `Shift tab` to move around the list.

`gg` would go to the top of the file
`Shift g` would go to bottom of the file

`netRW` is the plugin in built for vim that shows the tree view of the directory.

`:Ex` would open the current buffer with explorer view. 
`:Vex` would open a new buffer on the vertical split
`:Sex` would open a new buffer on the horizontal split

`Ctrl w` to enter `WINDOW MODE` and then `hjkl` to move around. 

`Ctrl w s` to open a horizontal split
`Ctrl w v` to open a vertical split

`Ctrl w o` would close all the buffers and leave only the current one open.

`:Vex` can be annoying to do so Introducing remaps

```
let mapleader=" "
nnoremap <leader>pv :Vex<CR>
```

`mapleader` is some key that we indicate to the vim saying this is start of some special command.

`nnoremap <leader>pv :Vex<CR>` can be broken into

```
n // Mode (INSERT, VISUAL, NORMAL, VISUAL-LINE)
nore // no repeat execution, -> This would prevent the RHS from executing on its own
map <leader>pv :Vex<CR> // This is what we need to execute when we enter LHS
```

`LHS` => `<leader>pv`
`RHS` => `:Vex <CR>` This is executed when we type `LHS`

> Now instead of doing `:Vex` we can just do `<space>pv` for the project view to show

Since `<space>` is mapped as leader key, everytime `<space>` is pressed , it waits for a follow up before it actually moves to the left.

> `<space>` === `l` normally

`:e <SEARCH_FILES` can be used to pull up and find files with name strings or regex too.
`tab` `Shft tab` can be used to navigate. `Ctrl d` to expand on all the options that is possible

> But this is still not useful as a fuzzyfinder is. Telescope is a much better tool for this

Marks can be used to bookmark files or places in a file.

`m` followed by `A` would mark a file on the global buffer. 
Now `m` followed by `B` would mark another file on the global buffer
To swtich between the two marked files we can `'A` and `'B` and swtich between them both.

> Capital letters are global buffers for across files, while lower case letters are used to mark places inside a given file.

`:reg` has a `"%` and `"#` location. If noticed. 
`"%` is the current file that is in scope
and `"#` is the previously accessed file.
This makes us switch between them using `Ctrl ^` (`Ctrl + 6`) as they are stored in the `:reg` location.

> This is also the reason why `:so %` worked, cause we are sourcing the current file while editing `.vimrc` 

`:h jumplist` tracks a list of palces you have jumped using motions.
`Ctrl i` and `Ctrl o` to navigate between this list.
