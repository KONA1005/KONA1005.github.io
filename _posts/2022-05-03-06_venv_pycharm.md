---
title: " [가상환경] 파이참 "
date: 2022-05-03-06 
categories: VENV
---

# 가상환경 만들기_파이참

파이참으로 가상환경을 만들기에 앞서 ... VS Code 사용시 virtualenv venv가 안먹혔다..

가상환경 설치를 해봐도 안됐다...당황했다... 

# 내가 겪은 오류 —

- 가상환경을 만들때 git bash로 실행시 venv 파일이 생성이 되지 않았다.
- 쉽고 빠르게 파이참으로 가상환경을 만들어보자

## 1. 파이참 실행 후 New Project를 누른다.

## 2. 아래 사진처럼 설정을 해준다.

- Location 확인하기
    - 나는 바탕화면에 web 폴더를 만들어서 지정해줬다.
- Base interpreter : 버전 확인하기

![Untitled](/images/2022-05-03-06_venv_pycharm/Untitled.png)

## 3. Create를 누른다.

## 4. 터미널에 실행한다.

```bash
$ which python
```

- 경로가 맞는지 확인

## 5. 확인사항

```bash
$ python main.py
```

- Hi, PyCharm 나오나 확인 한다.

![Untitled](/images/2022-05-03-06_venv_pycharm/Untitled%201.png)