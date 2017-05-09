# VIM

## Getting help for Vim commands

Get help for Vim commands with `:help <command>`.

## Principles of Vim

The primary benefit of Vim is speed. Maximum speed can be obtained by recognizing that a good Vimmer keeps his or her hands on home row and avoids using arrow keys and other relatively slow interaction methods.

## Plugin Management

[Pathogen](https://github.com/tpope/vim-pathogen) is generally considered to be a good plugin manager.

## Current file

Display the current filepath with `:echo @%`

## Tabs

* Open a new tab with `:tabe`
* Go to next tab with `:tabn`
* Go to previous tab with `:tabp` or `:tabN`

## Windows

Switch between windows: `CTRL+ww`

## Treeview

[NERDTree](http://www.vim.org/scripts/script.php?script_id=1658) lets you explore directory trees. Launch with `:NERDTree`. Close the NERDTree window with `q`.

## Searching for files by name

[fzf](https://github.com/junegunn/fzf) is a great fuzzy search tool. See the README in that repo for install details.

Search for files with `:FZF`.

## Searching all files for a string

Use grep to search.

Example: `:grep -r --include="*.rb" shipping_cost ./`

Then use `:cl[ist]` and `:cn[ext]` to navigate results.

## Repeat Command

Repeat the last command with `@:`.
