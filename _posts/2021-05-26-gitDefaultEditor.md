---
title: MacOS에서 VSCode를 git default editor로 설정하는 방법
categories: [git]
comments: true
---

Windows에서는 git을 설치할때 설치화면에서 default editor를 선택하는 과정이 있지만, MacOS에서는 git을 homebrew로 설치하고

```zsh
brew install git
```

세부 설정 없이 설치가 바로 끝나기 때문에 default editor를 따로 설정해야합니다. 그 방법을 검색해보면

```zsh
git config --global core.editor "code --wait"
```

이 명령어를 쓰라는 경우가 대부분인데 이렇게 설정하면 저의 경우에는 에러가 났습니다.

```zsh
code .
```

명령어로 현재 디렉토리나 특정 디렉토리를 VSCode로 여는 것은 동작하는걸로 보아 shell이 VSCode의 경로는 갖고 있을텐데 git이 VSCode를 못 열더라고요.  
그래서 Application 디렉토리에 있는 VSCode 패키지의 내부 실행파일이 있는 경로까지 써서 이렇게 설정했고,

```zsh
git config --global core.editor "/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code --wait"
```

<b>잘 동작합니다.</b>
