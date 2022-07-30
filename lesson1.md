#### Vim Fundamentals

This repo will be entirely done from within a terminal. Let's hope I get out of vim.

`:h <OPTS>` This will get the help menu

OPTS
 - `buffer` Something that is to be written inside the files
 - `window` 
 - `split` Screen splits into two
 - `tab` more like a vscode tab but not a vscode tab too
 - `menu` RTFM (Read the Friendly Manual)
 - `motion` Any mouse movements are called as motions in vim

`:new` creates a horizontal split
`:vnew` creates a vertical split

vimL - vim editors language

`<C-a>` corresponds to (Control + a) 
`<CR>` is Enter
`<esc>` `<space>` `<tab>` are used too

- Anything that starts with `:` is a command

`:q` to exit from VIM

`i` to go to insert mode

`NORMAL` `VISUAL` `INSERT` `VISUAL-LINE` modes are the four modes available`

`ESC` or `Ctrl+c` to exit to normal mode. `Ctrl+c` might not work for all cases but works mostly.

- `:wq`  write and quit
- `:q!` force quit

`h` is left
`j` is jump down a line
`k` is kick back up
`l` is right

`x` is delete character under cursor

`zz` to recenter your screen

> The cursor would always jump to the farthest location it knew from the previous line. Hence the cursor jumps when you move around.

`w` would hop by word, hops to the word and not the delimiter
`b` reverse of what `w` does

`dd` delete the line
`Shift v d` select the line and delete it

`u` is undo

`yyp` yank the line and paste it below
`yy Shift p` yank the line and paste it above

`v` is visual mode. move around and select text shown as highlight.
`Shift v` is visual line mode, will select lines instead of just words.

"yanked" your visual region selected.

`:reg` would show the register memory.
Its a list of `"" 1, 2, 3, ... 9`.

`"" reg` is called the implicit register and `p` actually pastes what is in here.

`i` inserts to the left
`a` inserts to the right

`Shift i` will insert to the non white space begining of the line
`Shift a` will put you at the end of the line, including the white spaces and everything.

`o` is open below
`Shift o` is open above


