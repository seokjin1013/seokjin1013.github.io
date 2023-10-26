---
title: WSL에서 npm 설치하기
date: 2023-06-05 02:04 +0900
last_modified_at: 2023-10-26 22:03 +0900
category: [Environment Settings]
tag: [WSL Ubuntu, npm]
toc: false
---

### 문제 상황

WSL의 Ubuntu환경에서, jekyll의 [chirpy테마](https://github.com/cotes2020/jekyll-theme-chirpy)를 이용하기 위해 Node.js를 설치해야 했다.

### 해결법

[WSL 공식문서](https://learn.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl#install-nvm-nodejs-and-npm)를 참고하였다.

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash`
: nvm 설치한다. Node enVironment Manager를 축약한 말으로 node를 설치하기 위해 필요하다.

`command -v nvm`
: nvm이 설치되어있는지 확인한다. nvm이라고 출력되지 않으면 설치되지 않은 것이다. 터미널을 껐다 켜면 nvm이 인식되는 경우가 있다.

`nvm install node`
: node를 설치한다. npm도 동시에 설치된다.

`nvm ls`
: 설치된 node버전을 확인한다. N/A라고 표시되어있으면 설치되지 않은 것이다.

> 만약 `npm install`으로 설치했다면 [여기](https://sudo-minz.tistory.com/96)를 참고하여 완전히 제거하고 위 방법대로 다시 설치해야 한다. 그러지 않을 경우 chirpy테마에서 `tools/init`를 실행할 때 오류로 인해 배포할 때 필요한 자바스크립트 파일이 생성되지 않아서 배포가 불가능해진다. (`/assets/js/dist/page.min.js`)
{:.prompt-warning}