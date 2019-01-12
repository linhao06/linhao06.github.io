---
title: Hexo 리소스 GitHu에 배포
date: 2019-01-13 03:21:06
tags: GitHub, Hexo
---

멀티 디바이스에서 Hexo Blogs를 편집 배포하기 위하여 Hexo 리소스를 GitHub에 배포한다.

# 1. GitHub에 Hexo 소스 배포  #

배포할 리소스는 아래와 같습니다.

	1. scaffolds
	2. source
	3. .gitignore
	4. _config.yml
	5. package.json

Hexo를 배포한 GitHub Repository에 새로운 branch(hexo)를 생성하여 위를 리소스를 저장.


# 2. 새로운 환경에서 Hexo 실행 #

**준비작업**: 아래의 프로그램 Install

- [Git](https://git-scm.com/downloads "Git")
- [NodeJS](https://nodejs.org/en/ "NodeJS")


## 2.1 Hexo 설치 ##

	mkdir Blogs  #Blog폴더 생성
	cd Blogs
	npm install hexo-cli -g   #hexo 모듈 설치
	hexo init

위에서 생성한 scaffolds, source 자식폴더를 삭제.

## 2.2 GitHub에서 받은 리소스를 Hexo에 적용 ##

	git clone -b hexo --single-branch https://github.com/linhao06/linhao06.github.io temp

temp폴더내 전체문서를 위에서 생성한 Blogs폴더에 붙여넣음.

## 2.3 Indigo theme install ##

	cd Blogs
	git clone git@github.com:yscoder/hexo-theme-indigo.git themes/indigo

## 2.4 Hexo 실행 및 배포 ##

Hexo 실행

	hexo clean & hexo g & hexo s 

배포

	hexo d

방문

	https://linhao06.github.io/
