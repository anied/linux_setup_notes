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
- Customize Terminal appearance

#### Touchpad/Mouse

- Touch to click
- Lower right corner quick\*
- Set preferred mouse scroll

#### Other

- Add keyboard shortcut for nightlight
- Disable `Ctrl+Alt+Arrow` for switch workspace (as it encroaches on VSCode move to pane)\*
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
- Muse

#### Development

- VSCode
- Postman

### Terminal

- `nvm`/`node`/`npm`
- `git`
    - Change default main branch to `main`:
      `git config --global init.defaultBranch main`
    - Configure my user:
      ```
      git config --global user.email "you@example.com"
      git config --global user.name "Your Name"
      ```
    - Add [my aliases](https://gist.github.com/anied/fb7b9abdfe861205b23ed78be2a05a1a)
    - Configure Github PAT
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
