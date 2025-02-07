# dotfiles

## Initial Set Up
1. Run "sendit.sh" script
2. echo ".cfg" >> .gitignore
3. `git clone --bare <git-repo-url> $HOME/.cfg`
4. `alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
5. `config checkout`

you might get this:
`error: The following untracked working tree files would be overwritten by checkout:
    .bashrc
    .gitignore
Please move or remove them before you can switch branches.
Aborting`

therefore do this
`mkdir -p .config-backup && \
config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}`

[link to docs](https://www.atlassian.com/git/tutorials/dotfiles)

## Tech
- Iterm2
- Oh-my-zsh
- Powerlevel10k
- Vim
- Tmux
