# dev-env-macos

> Instructions and scripts allowing for the management of development environments on MacOS

## Summary

- Install [homebrew](https://docs.brew.sh/Installation)
  - If the user has administration capabilities install to the expected location
  - Otherwise install locally to remove the need for sudo use
- Install brew formulas
  - [coreutils](https://formulae.brew.sh/formula/coreutils)
  - [gnupg](https://gnupg.org)
- Install brew casks
  - [Altair GraphQL Client](https://altair.sirmuel.design)
  - [Draw.io](https://www.diagrams.net)
  - [GitHub Desktop](https://docs.github.com/en/desktop)
  - [GraphQL Playground](https://github.com/graphql/graphql-playground)
  - [Inkscape](https://inkscape.org)
  - [IntelliJ Community Edition](https://www.jetbrains.com/idea)
  - [iterm2](https://www.iterm2.com)
  - [macSVG](https://macsvg.org)
  - [Visual Studio Code](https://code.visualstudio.com)
- TBD: Install ITerm2 Fonts/Colors
- Install [ASDF](https://github.com/asdf-vm/) to manage multiple runtime versions with a single CLI tool
- Install [ASDF runtime plugins](https://github.com/asdf-vm/asdf-plugins)
  - GoLang
  - Java
  - JQ
  - Kotlin
  - NodeJS
  - Python
- Install [Oh-My-Zsh](https://ohmyz.sh)
- Install Oh-My-Zsh Custom Plugins/Themes
  - [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
  - [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- Set .zshrc preferences
  - [ZSH_THEME](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)="robbyrussell"
  - [HIST_STAMPS](https://github.com/ohmyzsh/ohmyzsh/wiki/Settings#hist_stamps)="yyyy-mm-dd"
  - [plugins](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins)
    - zsh-syntax-highlighting
    - zsh-autosuggestions
    - [zsh-brew-local](https://github.com/ve2caz/dev-env-macos/.oh-my-zsh/custom/plugins/zsh-brew-local)
    - brew
    - asdf
    - docker
    - git
    - golang
    - gradle
    - history
    - kubectl
    - kubectx
    - node
    - npm
    - vscode

## Before you begin

- Installing, updating or removing software is an administrative task and as such should be performed using an account with elevated privileges i.e. a member of the admin group
- Development is NOT an administrative task and as such should be performed using and account with lowered privileges i.e. a member of the staff group
- Unless otherwise specified all terminal commands are based on the new default zsh shell.
- Apple macOS Big Sur 11.16.1

## Install XCode

> *[Xcode is an integrated development environment (IDE) for macOS containing a suite of software development tools developed by Apple for developing software for macOS, iOS, watchOS, and tvOS.](https://en.wikipedia.org/wiki/Xcode)*

- ⌘ Space + *App Store* + ⏎
- Search for XCode in the search box
- Install XCode
- Go for coffee...
- Launch XCode and accept the license agreement
- Quit XCode

## Install XCode command line tools

> XCode doesn't install it's command line unilities by default

- ⌘ Space + *Terminal* + ⏎
- Execute the following commands in Terminal's shell

```zsh
% xcode-select --install
% xcode-select -p
```

- If the developer directory is `/Applications/Xcode.app/Contents/Developer` you can skip the next steps
- Execute the following commands in Terminal's shell (don't forget to change `<admin account>`)

```zsh
% sudo - <admin account>
% sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
% exit
```

> Update XCode command line tools

```zsh
Error: Your Command Line Tools are too outdated.
Update them from Software Update in System Preferences or run:
  softwareupdate --all --install --force

If that doesn't show you any updates, run:
  sudo rm -rf /Library/Developer/CommandLineTools
  sudo xcode-select --install

Alternatively, manually download them from:
  https://developer.apple.com/download/all/.
  You should download the Command Line Tools for Xcode XX.X.
```

## Install this repository locally

> Let's clone the repository to manage the development environments

- ⌘ Space + *Terminal* + ⏎
- In Terminal's shell execute the following commands

```zsh
% export GITHUB_ROOT=~/Documents/dev/github
% mkdir -p $GITHUB_ROOT
% cd $GITHUB_ROOT
% git clone https://github.com/ve2caz/dev-env-macos.git
% cd dev-env-macos
```

## Setup the development environment

```zsh
% ./scripts/setup.zsh
```

## Teardown the development environment

```zsh
% ./scripts/teardown.zsh
```
