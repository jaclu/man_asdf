# man_asdf
Display man page for installed versions of an asdf plugin.

## Requirements

- asdf (https://github.com/asdf-vm/asdf)

## Installation

#### 1. Preparation

Once you have entered the repo dir, designate destination by doing 

```bash
echo "/usr/local/bin" > .destination
```

Replace destination path with your preference if you do not want to use
/usr/local/bin

#### 2. Deploy

Any time the repo is updated, all you need to do is this. 
Since nothing will happen if there was no update, it is safe to always perform this step, in case you automate handling of this repo.

```bash
./deploy
```

First time you might need to do 

```bash
sudo ./deploy
```

If you dont have write privs to the destination. Further deploys will not need this since you are just updating this file, and it is owned by you.

## Usage

```bash
Syntax:  man_asdf [-h --help] asdf_command [alt_version]
  alt_version must still be installed in order to be viewed!

Displays man page asociated with an asdf command.
Please note that not all asdf commands come with man pages
in such cases you will get a notification stating such.

If current version is system, you will be informed that this
is the case and all installed versions will be listed.
If you suply a version, that versions man page will be displayed.

Examples: man_asdf python
          man_asdf python 3.9.2
```


As always any feedback is welcome!
