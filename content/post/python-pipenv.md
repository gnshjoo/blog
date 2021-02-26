---
title: "Python Pipenv 가상환경 셋팅하기"
date: 2020-10-08T17:31:53+09:00
categories: ["TIL", "Python"]
tags: ["python", "Django"]
cover: ""
draft: false
---

# 1. Python 가상환경 설정

Python3이 설치 되어있다는 가정하에 설명하도록 하겠다.

```shell
$ pip3 install pipenv
$ pipenv --version
pipenv, version 2020.6.2
```

pipenv을 사용하려면 디렉토리를 만들어 준 후 디렉토리로 이동한다.

```shell
$ mkdir django-test && cd django-test
$ pipenv shell
Courtesy Notice: Pipenv found itself running within a virtual environment, so it will automatically use that environment, instead of creating its own for any project. You can set PIPENV_IGNORE_VIRTUALENVS=1 to force pipenv to ignore that environment and create its own instead. You can set PIPENV_VERBOSITY=-1 to suppress this warning.
Warning: the environment variable LANG is not set!
We recommend setting this in ~/.profile (or equivalent) for proper expected behavior.
Creating a virtualenv for this project…
Pipfile: /Users/david/PROJECT/django-test/Pipfile
Using /usr/local/opt/python@3.8/bin/python3 (3.8.5) to create virtualenv…
⠏ Creating virtual environment...created virtual environment CPython3.8.5.final.0-64 in 573ms
  creator CPython3Posix(dest=/Users/david/.local/share/virtualenvs/django-test-0W9m7BVl, clear=False, global=False)
  seeder FromAppData(download=False, pip=latest, setuptools=latest, wheel=latest, via=copy, app_data_dir=/Users/david/Library/Application Support/virtualenv/seed-app-data/v1.0.1)
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator

✔ Successfully created virtual environment!
Virtualenv location: /Users/david/.local/share/virtualenvs/django-test-0W9m7BVl
Creating a Pipfile for this project…
Launching subshell in virtual environment…
 . /Users/david/.local/share/virtualenvs/django-test-0W9m7BVl/bin/activate
  ~/PROJECT/django-test                                                                                                                                                                            17:49:18
❯  . /Users/david/.local/share/virtualenvs/django-test-0W9m7BVl/bin/activate
```

pipenv 활성화가 된다.

가상환경이 생성된 곳에서 이 명령어를 넣어주면

```shell
$ pipenv shell
```

똑같이 가상환경이 활성화가 된다.
