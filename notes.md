# Notes

## Installation workflow

1. Clean up old references

``` bash
# make sure to backup any .config/nvim settings
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim
rm -rf ~/.local/state/nvimk
```

2. Fork [original repo](https://github.com/nvim-lua/kickstart.nvim)
3. Clone from your github repo
4. `git remote add upstream <original repo>`
5. `git fetch upstream`
6. `git merge upstream` to resolve any conflicts
7. `git remote set-url origin <your repo>`
7. `git push origin master`
6. `git checkout -b <your branch>`
7. Commit changes and then `git push origin <your branch>`
8. Approve PR and merge into master

## Shortcuts summary

1. `:help [package]` = [vim] open manual for package
2. `n %` = [vim] toggle between 'kalsdjfodsaif' brackets {} [] ()
3. `n f|t<letter>` = [vim] jump to (for f) or before (for t) a letter. `;` to go to next instance and `,` to go back 
4. `n ctrl+o|i` = [vim] go next/previous of jumplist. use `:jumps` to see the full list
5. `n J` = [vim] = join line
6. `n ctrl+d|u` = [vim] scroll through buffer list
7. `n ctrl+a` = [vim] increment number
8. `n ctrl+x` = [vim] decrement number
9. `n gv` = [vim] go to last visual selection
10. `v g+ctrl+a` = [vim] increment number. Useful when trying to reenumerate a list of numbers
11. `:'<,'>s/\v[0-9]+/0` = [vim] replace all numbers with 0. Use this in combo with `gv` and `g+ctrl+a` in order to reenumerate a list of numbers
12. `:%s/\v<regex>/<replacement>/<options>` = [vim] search and replace entire file. Tip: use the fighting one eyed kirby (.) to capture a group then reference it with \1..n. For options, use `gcI` for sane defaults
13. `:'<,'>s/\v<regex>/<replacement>/<options>` = [vim] search and replace highlighted texts. Tip: use ^ for beginning of line and $ for end of line additions. `\v` sets the regex to very magic mode so that some metachars do not need to be escaped
14. `:%s/\v'(.{-})'/\1` = [vim] Capture the first occurence of single quotes. Useful when editing json. `{-}` is the vim way of a non greedy match
15. `ctrl+v` = [vim] visual block mode
16. `n >>|<<` = [vim] move text by the shiftwidth amount   
17. `n <leader>;o` = [custom-vim] open quickfix list (a list of filename and location). replaces `:copen`
18. `n <leader>;x` = [custom-vim] close quickfix list. replaces `:cclose`
19. `n <leader>;n` = [custom-vim] go to next line in quickfix list. replaces `:cnext`
20. `n <leader>;p` = [custom-vim] go to previous line in quickfix list. replaces `:cprev`
21. `n d|c|y+a` = [nvim] delete or yank everything inside and including the text. Most useful options are `w` (word), `'` (string), `{` (bracket), `t` (tag)
22. `n d|c|y+i` = [nvim] delete or yank everything inside and excluding the text. Most useful options are `w` (word), `'` (string), `{` (bracket), `t` (tag)
23. `n ctrl+^` = [nvim] go to previous buffer
24. `:so $MYVIMRC` = [nvim] reboot source file. In this case it is init.lua
25. `n <leader>q` = [nvim] open diagnostics quickfix list
26. `n [c` = [nvim] go to next git change
27. `:lua vim.diagnostics.enable(not diagnostics.is_enabled())` = [nvim] example of running lua directly from command mode. For this example, it toggles the diagnostic linter
28. `n <leader>;l` = [custom-nvim] toggle the diagnostic linter
29. `n ctrl+w+v` = [wincmd] vertical screen split
30. `n ctrl+w+s` = [wincmd] horizontal screen split
31. `n ctrl+w+w` = [wincmd] toggle between screen splits
32. `n ctrl+h|j|k|l` = [wincmd] toggle between screen splits in a specific direction
33. `n ctrl+w+o` = [wincmd] close all other windows
34. `n <leader>sf` = [telescope] search for file
35. `n ctrl+q` = [telescope] add result to quickfix list
36. `n <leader>sd` = [telescope] open diagnostics search list
37. `n <leader>sw` = [telescope] search for word
38. `n <leader>st` = [custom-telescope] search for git files
39. `n gr` = [mason-LSP] go to function reference
40. `:Mason` = [mason-LSP] show installed LSPs
41. `shift+k` = [mason-LSP] show type and/or function signature
42. `v gc` = [mason-LSP] toggle comment
43. `v gw` = [mason-LSP] format code 
44. `n shift+8` = [hlsearch] highlight all instances of the word on cursor
45. `n \` = [treesitter] toggle treesitter file explorer side nav
46. `n <leader>;c` = [custom-cloak] toggles cloak. replaces `:CloakToggle`


### Todo

- edit all highlighted texts at once
- format code with proper indentation
- adding, removing, renaming files and folders
- node debugger
- tab spacing
- move highlighted text with tab
- tmux commands (going back and forth projects - can it go into whichkeys?)
- shortcut to go to nvim config to quickly edit/update. git pull, :Lazy sync
- git diff shower (fugitive)
- closing all files and opening new ones
- handling other languages like Japanese or Spanish

### Packages to consider 

``` bash
cloak
fugitive
undotree
harpoon
vim-visual-multi
prettier
```


### Links

- [Multi selection](https://www.youtube.com/watch?v=N-X_zjU5INs)
- [Init nvim setup](https://www.youtube.com/watch?v=-ybCiHPWKNA)
- [nvim from scratch](https://www.youtube.com/watch?v=w7i4amO_zaE)
- [Multi selection without plugins](https://vonheikemen.github.io/devlog/tools/how-to-survive-without-multiple-cursors-in-vim/)
