# README

This repository contains the source files for [githubcampus.lafayette.edu](githubcampus.lafayette.edu). It uses the Jekyll static site builder. For the best experience, we recommend also setting up [devenv](https://devenv.sh) for manage your local authoring environment.

## One-time setup

### devenv.sh

Following the [getting started instructions](https://devenv.sh/getting-started/) on devenv.sh to install Nix and devenv on your local workstation. You may also need to add local user as a trusted user for the Nix environment. Edit `/etc/nix/nix.conf` and add or modify the following line:

```bash
trusted-users = root <your username>
```

Then restart the Nix daemon:

```bash
sudo launchctl kickstart -k system/org.nixos.nix-daemon
```

### This repository

Clone this repository to your local workstation. If you're not using devenv.sh, ensure that you have a working Ruby environment and run `bundle install` to setup the necessary gems.

## Usage

You can use devenv.sh to set up a local authoring environment. Within the repository, use `devenv up` to install the gems and start the Jekyll server. The site will be accessible at http://localhost:4000. The manual version of the Jekyll command is `bundle exec jekyll serve --watch`. You can use `devenv shell` to launch a bash shell with the correct ruby environment; it will not start the Jekyll service.