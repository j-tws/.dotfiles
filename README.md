# Managing dotfiles via bare repository

My dotfiles is managed using bare repository. Read here for more:
https://www.atlassian.com/git/tutorials/dotfiles

## To install dotfiles in new system
1. Make sure to have this alias in your shell:
```sh
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
```

2. Make sure source repository ignores the folder when you clone it, so you don't create weird recursion problems:
```sh
echo ".cfg" >> .gitignore
```

3. Clone dotfiles into a bare repostiry at `$HOME`
```sh
git clone --bare https://github.com/j-tws/.dotfiles.git $HOME/.cfg
```

4. Check content of bare repostiry:
```sh
config checkout
```

5. If you have a failed message like:
```sh
error: The following untracked working tree files would be overwritten by checkout:
    .bashrc
    .gitignore
Please move or remove them before you can switch branches.
Aborting
```

This is because your $HOME folder might already have some stock configuration files which would be overwritten by Git. The solution is simple: back up the files if you care about them, remove them if you don't care. I provide you with a possible rough shortcut to move all the offending files automatically to a backup folder:

```sh
mkdir -p .config-backup && \
config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}
```

6. Set the flag `showUntrackedFiles` to no on this specific (local) repository:
```sh
config config --local status.showUntrackedFiles no
```

7. Done! You can then add, commit and push files from there:
```sh
config add .zshrc
config commit -m "update .zshrc file"
config push
```

## Exploration
Create a simple script to remember all these steps and upload to bitbucket, create a short url and call it like:
```sh
curl -Lks http://bit.do/cfg-install | /bin/bash
```