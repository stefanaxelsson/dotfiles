# Stefan's dotfiles


## Installation

### Using Git and the bootstrap script

You can clone the repository wherever you want. (I like to keep it in `~/Documents/Projects/dotfiles`, with `~/dotfiles` as a symlink.) The bootstrapper script will pull in the latest version and copy the files to your home folder.

```bash
git clone https://github.com/stefanaxelsson/dotfiles.git && cd dotfiles && source install.sh
```

To update, `cd` into your local `dotfiles` repository and then:

```bash
source install.sh
```

Alternatively, to update while avoiding the confirmation prompt:

```bash
set -- -f; source install.sh
```

### Git-free install

To install these dotfiles without Git:

```bash
cd; curl -#L https://github.com/stefanaxelsson/dotfiles/tarball/master | tar -xzv --strip-components 1 --exclude={README.md,install.sh,LICENSE}
```

To update later on, just run that command again.

### Specify the `$PATH`

If `~/.path` exists, it will be sourced along with the other files, before any feature testing takes place.

Here’s an example `~/.path` file that adds `/usr/local/bin` to the `$PATH`:

```bash
export PATH="/usr/local/bin:$PATH"
```

### Add custom commands without creating a new fork

If `~/.extra` exists, it will be sourced along with the other files. You can use this to add a few custom commands without the need to fork this entire repository, or to add commands you don’t want to commit to a public repository.

You could also use `~/.extra` to override settings, functions and aliases from my dotfiles repository. It’s probably better to fork instead, though.

### Sensible OS X defaults

When setting up a new Mac, you may want to set some sensible OS X defaults:

```bash
./.osx
```