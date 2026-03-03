# Man_asdf

Display man page for installed versions of asdf plugins.
(Assuming it provides a man page)
If no matching asdf command is found the entire command line is handed to the
system man, so `man-asdf` can be soft-linked as `man` and be put before sys bins
in the path, and handle all man calls!

## Requirements

- asdf [asdf GitHub page](https://github.com/asdf-vm/asdf)

- At least one plugin and version of that installed - otherwise there is
  nothing to show man pages for...

## Installation

Either softlink man-asdf to a PATH location, or if you want more control over
what is in your path do as follows

### 1. Preparation

Once you have entered the repository dir, designate destination by doing

```bash
echo "/usr/local/bin" > .destination
```

Replace destination path with your preference if you do not want to use
/usr/local/bin

### 2. Deploy

Any time the repository is updated, and you want to use this new version,
all you need to do is this:

Since nothing will happen if there was no update, it is safe to always perform
this step, in case you automate handling of this repository.

```bash
./deploy
```

First time you might need to do

```bash
sudo ./deploy
```

If you don't have write privs to the destination. Further deploys will not
need this since you are just updating this file, and it is owned by you.

## Tested successfully with

- nodejs
- python
- tmux

## Usage

```text
Syntax:  man-asdf [-h --help] page [alt_version]
     OR: man-asdf {options and params just like for normal man}

If page was not an asdf_comman, the system man is used instead,
with full cmd line, So this can be a symbolic link for `man`
and put in PATH before the normal `man`

If this is an asdf command, its man page will be displayed
Please note that not all asdf commands come with man pages
in such cases you will get a notification stating such.

If you supply a version, that versions man page will be displayed.
When no version is specified, the current asdf version is assumed.

Examples: man-asdf python
          man-asdf python 3.9.7
          man-asdf python system
```

As always any feedback is welcome!
