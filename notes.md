# Installation workflow

1. Clean up old references

``` bash
# make sure to backup any .config/nvim settings
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim
rm -rf ~/.local/state/nvimk
```

2. Fork [original repo](https://github.com/nvim-lua/kickstart.nvim)
3. Clone from your github repo
4. `git remove add upstream <original repo>`
5. `git fetch upstream`
6. `git merge upstream` to resolve any conflicts
7. `git push origin master`
6. `git checkout -b <your branch>`
7. Commit changes and then `git push origin <your branch>`
8. Approve PR and merge into master
