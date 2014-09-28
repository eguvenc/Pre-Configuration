
## Setting Git on Your Local Ubuntu

-----

### Installation Git

<a href="https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04">https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04</a>

#### Git Ssh Key Setup

<a href="https://help.github.com/articles/generating-ssh-keys">https://help.github.com/articles/generating-ssh-keys</a>


### First Time Configuration

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

### Checking Your Settings

If you want to check your settings, you can use the git config --list command to list all the settings Git can find at that point:

```
$ git config --list
user.name=Scott Chacon
user.email=schacon@gmail.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
```

### Your Diff Tool
Another useful option you may want to configure is the default diff tool to use to resolve merge conflicts. Say you want to use vimdiff:

```
$ git config --global merge.tool vimdiff
```

### Cloning your repository

```
$ git clone git@github.com:myProduct/software.git
```

### Initializing to Submodules

```
$ git submodule init
$ git submodule update
```