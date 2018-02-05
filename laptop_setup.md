## Installations (Ubuntu)
 - Git, Make, Pandoc, Texlive: `sudo apt-get install git build-essential pandoc texlive-full`
 - [Anaconda](https://www.continuum.io/downloads)
 - [R](https://cran.rstudio.com/)
 - [RStudio](https://www.rstudio.com/products/rstudio/download/)
 - [Chrome](https://www.google.ca/chrome/browser/desktop/index.html)
 - [Slack](https://slack.com/downloads/linux)
 - [Atom](https://atom.io/)
   - Atom --> Install Shell Commands
   - [LaTeX](https://atom.io/packages/latex): `apm install latex` and `apm install language-tex`
   - [Markdown](https://atom.io/packages/markdown-preview-plus): `apm install markdown-preview-plus`
 - [Spotify](https://www.spotify.com/ca-en/download/other/)
 - [Skype](https://www.skype.com/en/download-skype/skype-for-computer/)
 - [Dropbox](https://www.dropbox.com/downloading)
 - [Matlab](https://www.mathworks.com/downloads/)
 - [Docker](https://www.docker.com/community-edition#/download)
 

## Extra git stuff

#### Gitignore
In the file `~/.gitignore_global` put

```
.DS_Store
.ipynb_checkpoints
*~
.Trashes
.RHistory
__pycache__
~$*
```

and then execute `git config --global core.excludesfile '~/.gitignore_global'`

#### Defaults

```
git config --global core.editor gedit
```
(or `atom` or whatever) 

Also

```
git config --global user.name "Xinbin Huang"
git config --global user.email xbhuang93@hotmail.com
```

#### Bashrc

In `~/.bash_profile` add the following aliases:

```
alias update='bash ~/../../update.sh' (git pull files for different repos
alias l="git status"
alias jp="jupyter notebook"
```

_This following part need to double-check_
```
# Git branch in prompt.
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

#### set up ssh key(s)

Following instructions at https://help.github.com/articles/generating-an-ssh-key/



_the following parts need to double-check_

And then `ssh-add -K ~/.ssh/id_rsa` to store the passphrase in Keychain.

Then add the following to `~/.ssh/config`:

```
Host *
  UseKeychain yes
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_rsa
```

so that you don't need to do this everytime you login (see [here](http://apple.stackexchange.com/questions/48502/how-can-i-permanently-add-my-ssh-private-key-to-keychain-so-it-is-automatically)).
