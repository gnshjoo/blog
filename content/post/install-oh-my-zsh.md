---
title: "Install Oh My Zsh"
date: 2020-10-11T20:42:28+09:00
categories: ["terminal"]
tags: ["oh-my-zsh"]
cover: ""
draft: false
---

#  Iterm2 설정방법
터미널을 사용하면서 다른 개발자들의 터미널들을 보면서 무슨 쉘 써요 ? 
무슨 테마써요 ..? 이렇게 많이 물어보곤 한다. 
그래서 내가 설정한 테마를 공유하려고 한다.

### 1. brew 패키지를 설치합니다.
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
homebrew는 Apple or Linux 시스템에서 제공하지 않는 유용한 패키지 관리자입니다.

### 2. iterm2 설치
```shell
brew install cask
brew cask install iterm2
```
맥 기본 터미널보다 많이 쓰는 iterm2를 사용합니다

### 3. Oh-My-Zsh / zsh 설치합니다.
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
brew install zsh
```

설치를 완료하면 원래 보던 터미널이 아닌 다른 테마가 보일 것입니다.
vi .zshrc
```shell
  1 # If you come from bash you might have to change your $PATH.
  2 # export PATH=$HOME/bin:/usr/local/bin:$PATH
  3
  4 # Path to your oh-my-zsh installation.
  5 export ZSH="/Users/shjoo/.oh-my-zsh"
  6 ZSH_DISABLE_COMPFIX="true"
  7
  8 # Set name of the theme to load --- if set to "random", it will
  9 # load a random theme each time oh-my-zsh is loaded, in which case,
 10 # to know which specific one was loaded, run: echo $RANDOM_THEME
 11 # See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
 12 ZSH_THEME="robbyrussell"
```
기본 테마는 robbyrussell 되어있습니다. 자기가 원하는 테마를 설정해주면 됩니다.
### 4. Fira code 설치
```shell
brew cask install homebrew/cask-fonts/font-fira-code
```
자신이 원하는 테마에 맞는 폰트를 설치해서 설정을 해주면 됩니다.
저는 spaceship 이라는 테마를 사용할 것이기 떄문에 fira code 폰트를 사용했다.

### 5. Spaceship 설치

![Example image](/img/ohmyzsh1.png)

[GitHub - denysdovhan/spaceship-prompt: A Zsh prompt for Astronauts](https://github.com/denysdovhan/spaceship-prompt) 애서 확인할 수 있다.
```shell
# themes에 spaceship에 git clone 저장
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1

# spaceship.zsh-theme로 custom themes디렉토리에 저장
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme" 
```
.zshrc에 ZSH_THEME=“spaceship”에 설정하면 됩니다.
하지만 처음에 설정하게 되면 폰트가 맞지 않아 폰트가 깨져 보일것이다. iterm2 setting에서 

![Example image](/img/ohmyzsh2.png)

Font -> Fira code로 바꾸면 깨지던 폰트가 정상으로 돌아온다.
spaceship 테마에는 이모지를 설정할 수 있으며 자신에 맞게 설정 할 수 있습니다.
설정을 하기 위해서는 ~/.spaceship_config 파일이 필요합니다.
https://github.com/denysdovhan/spaceship-prompt/blob/master/docs/Options.md 이곳에 사용할 수 있는 옵션들이 있으며
config 파일을 설정해준 뒤 .zshrc에 source .spaceship_config 명령어를 추가해주면 사용할 수 있습니다.