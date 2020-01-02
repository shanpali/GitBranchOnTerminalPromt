# GitBranchOnTerminalPromt
Showing current branch on terminal prompt (Mac)


# Open ~/.bash_profile in your favorite editor 

```Start up Terminal.
Type "cd ~/" to go to your home folder.
Type "touch . bash_profile" to create your new file.
Edit . bash_profile with your favorite editor (or you can just type "open -e . bash_profile" to open it in TextEdit).
Type ". . bash_profile" to reload . bash_profile and update any functions you add.
```


# Add the following content to the bottom in bash_profile.
# Git branch in prompt.

```sh

parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

By MARTIN FITZPATRICK at http://martinfitzpatrick.name/article/add-git-branch-name-to-terminal-prompt-mac/
