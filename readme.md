# Linux Setup Notes

## Overview

This document is intended to record all the things I usually need to do when I spin up a new Linux distro on my machine.  You can use it if you want, but it's probably most useful for people who are me or happen to like to setup their machines exactly like I do.  Some of these items may eventually be automated into a bash script.

## Dotfiles

_PENDING_

## Customize Grub

_PENDING_

## OS Tweaks

#### Appearance

- Change Background
- Switch to Dark Mode\*
- Autohide/show Dock
    ```
    sudo dnf install gnome-shell-extension-dash-to-dock
    ```
    Customize as needed
- Customize Terminal appearance

#### Touchpad/Mouse

- Touch to click
- Lower right corner quick\*
- Set preferred mouse scroll direction
- Gesture support: https://ubuntuhandbook.org/index.php/2022/06/touchpad-gestures-ubuntu-22-04-xorg/

#### Other

- Add keyboard shortcut for nightlight
- Add keyboard shortcut to show desktop (if applicable)
  - _[Super User: Is there a Gnome Shell shortcut to minimize a window?](https://superuser.com/questions/1130388/is-there-a-gnome-shell-shortcut-to-minimize-a-window)_
- Disable `Ctrl+Alt+Arrow` for switch workspace (as it encroaches on VSCode move to pane)\*
  - _[Ask Ubuntu: How to disable the shortcut Ctrl-Alt-Arrow in GNOME 3.8](https://askubuntu.com/questions/315625/how-to-disable-the-shortcut-ctrl-alt-arrow-in-gnome-3-8)_
  - _[Ask Ubuntu: Where does Ubuntu store its keyboard shortcut configuration?](https://askubuntu.com/questions/101226/where-does-ubuntu-store-its-keyboard-shortcut-configuration)_
- NVidia?
- Figure out special characters

## Software To Install

### Desktop Software & Adjustments

#### Productivity/Basics

- Chrome
    - Google Chat
    - Google Messages

#### Graphic Design

- Inkscape
- Gimp

#### Media

- VLC
- Audacity
- MuseScore

#### Development

- VSCode
- Postman
- FileZilla

### Terminal

- `nvm`/`node`/`npm`
  - [`nvm` Github page](https://github.com/nvm-sh/nvm)
  - ```
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    nvm use node
    nvm install node
    ```
- `git`
    - Change default main branch to `main`:
      `git config --global init.defaultBranch main`
    - Configure my user:
      ```
      git config --global user.email "you@example.com"
      git config --global user.name "Your Name"
      ```
    - Add [my aliases](https://gist.github.com/anied/fb7b9abdfe861205b23ed78be2a05a1a)
      ```
      # A list of all the git aliases I've been cultivating over the years

      # Nice logs
      git config --global alias.l '! git log --graph --decorate --branches --remotes --color=always | less -r'
      # Nice condensed logs
      git config --global alias.lp '! git log --graph --decorate --branches --remotes --pretty=format:"%C(auto) %h %d %s" --color=always | less -r'
      # Diff
      git config --global alias.d '! git diff --color=always | less -r'
      # Status
      git config --global alias.s 'status'
      # Clear all changes and untracked files
      git config --global alias.wipe '! git reset --hard && git clean -f -d'
      # See all aliases
      git config --global alias.aliases '! git config --get-regexp alias'
      ```
    - Configure Github PAT
        - [Overview](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)
        - [Token Generation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
        - [Github Credential Manager](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git)
        - [Credential Stores (necessary for GCM on Linux)](https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/credstores.md)
        - This approach sets the GCM on Ubuntu with the git built-in cache with a one-hour timeout:
            ```sh
            # configure credential store
            # https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/credstores.md#gits-built-in-credential-cache
            git config --global credential.credentialStore cache
            git config --global credential.cacheOptions "--timeout 48000"

            # install GCM
            # (get path from https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md#debian-package)
            sudo dpkg -i <path-to-package>
            git-credential-manager configure
            ```
    - Add autocomplete
    - Customize Prompt
      - Derived from https://gist.github.com/nisbeti/3d1c66bbb8f5cd83c2bce3ce05a7d58f
      - Also involves adding [this `git-prompt.sh`](https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh) to home directory
      - Adds this snippet to the bottom of my `.bashrc`:
        ```sh
        # Udacity Git Prompt -- https://gist.github.com/nisbeti/3d1c66bbb8f5cd83c2bce3ce05a7d58f
        # colors!
        green="\[\033[0;32m\]"
        blue="\[\033[0;34m\]"
        purple="\[\033[0;35m\]"
        reset="\[\033[0m\]"

        # Change command prompt
        source ~/git-prompt.sh
        export GIT_PS1_SHOWDIRTYSTATE=1
        # '\u' adds the name of the current user to the prompt
        # '\$(__git_ps1)' adds git-related stuff
        # '\W' adds the name of the current directory
        export PS1="$purple\u$green\$(__git_ps1)$blue \W $ $reset"

        ### ENDS Git prompt customization
        ```
- `less` (seems pre-installed?)
- fake `pbcopy`
  - Reference: https://superuser.com/questions/288320/whats-like-osxs-pbcopy-for-linux
  - _(requires install of `xsel`)_
  - Adds the following to the bottom of `.bashrc`
    ```sh
    # START Adds pbcopy alias - https://superuser.com/questions/288320/whats-like-osxs-pbcopy-for-linux
    alias pbcopy='xsel --clipboard --input'
    alias pbpaste='xsel --clipboard --output'
    # END pbcopy alias
    ```
- `neofetch` - https://github.com/dylanaraps/neofetch
- `htop` - https://htop.dev/downloads.html


\* (Might require Gnome Tweaks)
