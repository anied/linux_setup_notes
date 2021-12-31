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
- Autohide/show Dock\*
- Customize Terminal appearance &#9989;

#### Touchpad/Mouse

- Touch to click &#9989;
- Lower right corner quick\*
- Set preferred mouse scroll direction &#9989;

#### Other

- Add keyboard shortcut for nightlight
- Add keyboard shortcut to show desktop (if applicable) &#9989;
  - _[Super User: Is there a Gnome Shell shortcut to minimize a window?](https://superuser.com/questions/1130388/is-there-a-gnome-shell-shortcut-to-minimize-a-window)_
- Disable `Ctrl+Alt+Arrow` for switch workspace (as it encroaches on VSCode move to pane)\* &#9989;
  - _[Ask Ubuntu: How to disable the shortcut Ctrl-Alt-Arrow in GNOME 3.8](https://askubuntu.com/questions/315625/how-to-disable-the-shortcut-ctrl-alt-arrow-in-gnome-3-8)_
  - _[Ask Ubuntu: Where does Ubuntu store its keyboard shortcut configuration?](https://askubuntu.com/questions/101226/where-does-ubuntu-store-its-keyboard-shortcut-configuration)_
- NVidia?
- Figure out special characters

## Software To Install

### Desktop Software & Adjustments

#### Productivity/Basics

- Chrome &#9989;
    - Google Chat &#9989;
    - Google Messages &#9989;

#### Graphic Design

- Inkscape &#9989;
- Gimp &#9989;

#### Media

- VLC
- Audacity &#9989;
- MuseScore &#9989;

#### Development

- VSCode &#9989;
- Postman &#9989;
- FileZilla &#9989;

### Terminal

- `nvm`/`node`/`npm`
- `git`
    - Change default main branch to `main`: &#9989;
      `git config --global init.defaultBranch main`
    - Configure my user: &#9989;
      ```
      git config --global user.email "you@example.com"
      git config --global user.name "Your Name"
      ```
    - Add [my aliases](https://gist.github.com/anied/fb7b9abdfe861205b23ed78be2a05a1a)
    - Configure Github PAT &#9989;
        - [Overview](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)
        - [Token Generation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
        - [Github Credential Manager](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git)
    - Add autocomplete
    - Customize Prompt
- `less`
- fake `pbcopy`
- `neofetch`
- `htop`


\* (Might require Gnome Tweaks)
