# man_asdf

Display man page for installed versions of asdf plugins. (Assuming it provides a man page)

## Requirements

- asdf (https://github.com/asdf-vm/asdf)

- At least one plugin and version of that installed - otherwise there is nothing to show man pages for...

## Installation

Either softlink man_asdf to a PATH location, or if you want more control over what is in your path do as follows

##### 1. Preparation

Once you have entered the repo dir, designate destination by doing

```bash
echo "/usr/local/bin" > .destination
```

Replace destination path with your preference if you do not want to use
/usr/local/bin

##### 2. Deploy

Any time the repo is updated, all you need to do is this.
Since nothing will happen if there was no update, it is safe to always perform this step, in case you automate handling of this repo.

```bash
./deploy
```

First time you might need to do

```bash
sudo ./deploy
```

If you don't have write privs to the destination. Further deploys will not need this since you are just updating this file, and it is owned by you.

## Tested successfully with

- nodejs
- python
- tmux

## Usage

```
Syntax:  man_asdf [-h --help] asdf_command [alt_version]
  alt_version must still be installed in order to be viewed!

Displays man page associated with an asdf command.
Please note that not all asdf commands come with man pages
in such cases you will get a notification stating such.

If current version is system, you will be informed that this
is the case and all installed versions will be listed.
If you supply a version, that versions man page will be displayed.
When no version is specified, the current asdf version is assumed.

Examples: man_asdf python
          man_asdf python 3.9.2
```

As always any feedback is welcome!
