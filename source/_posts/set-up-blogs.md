---
title: Hexo Blog 만들기
date: 2019-01-12 02:57:10
tags: GitHub, Hexo
---

## 1. GitHub에서 public respository 만들기  ##

    public repository: linhao06.github.io

PS:Repository이름은  GitHub계정뒤에 github.io를 추가하는 형식으로 repository 이름 지정

## 2. Git와 NodeJS 프로그램 설치 ##

- [Git](https://git-scm.com/downloads "Git")
- [NodeJS](https://nodejs.org/en/ "NodeJS")

## 3. Hexo 사용 ##

### 3.1 Hexo 설치 ###

	mkdir Blogs  #Blog폴더 생성
	cd Blogs
	npm install hexo-cli -g   #hexo 모듈 설치
	hexo init
	npm install
	hexo g #페이지 생성 혹은 hexo generate
	hexo s # 서버 시작 혹은 hexo server

----------

### 3.2 Hexo 페이지 생성 ###

	hexo new "문장명" #문장생성
	hexo new page "페이지명" #페이지 생성"

----------

### 3.3 Hexo theme 추가  ###
 
	cd Blogs
	git clone git://github.com/tommy351/hexo-theme-light.git themes/light
	cd themes/light
	git pull

위의 명령 실행후 Root폴더 _config.yml파일에서 theme속성 편집

	# Extensions
	## Plugins: https://hexo.io/plugins/
	## Themes: https://hexo.io/themes/
	theme: light

### 3.4 Hexo 생성한 페이지를 GitHub에 배포  ###

위의 _config.yml파일에서 deploy 속성 편집

	# Deployment
	## Docs: https://hexo.io/docs/deployment.html
	deploy:
	    type: git
	    repo: git@github.com:linhao06/linhao06.github.io.git  #这里的网址填你自己的
	    branch: master   


hexo deploy 모듈 install

	cd Blogs
	npm install hexo-deployer-git --save   

SSH key 생성 및 GitHub에 등록 

	cd ~/.ssh
	ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
	[Enter][Enter][Enter] #세번쯤 Enter key 클릭
	ls #보면 
	clip < id_rsa.pub

**참고**:

[Generating a new SSH key and adding it to the ssh-agen](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/ "Generating a new SSH key and adding it to the ssh-agent")

GitHub에 로그인후 **SSH and GPG Key** Tab에서 생성한 SSH Key내용을 추가.

	cd Blogs
	ssh -T git@github.com

GitHub연결 테스트후 성공하면 아래 메세지 출력

	Hi linhao06! You've successfully authenticated, but GitHub does not provide shell access.

Git 개인정보 설치

	git config --global user.name "이름"
	git config --global user.email "메일주소"

배포 

	hexo d

Blog 방문

	https://linhao06.github.io/

### 3.5 Hexo 명령어  ###

	hexo n == hexo new
	hexo g == hexo generate
	hexo s == hexo server
	hexo d == hexo deploy


**참고:**

[我是如何利用Github Pages搭建起我的博客，细数一路的坑](https://www.cnblogs.com/jackyroc/p/7681938.html "我是如何利用Github Pages搭建起我的博客，细数一路的坑")

[好用的Markdown编辑器一览](https://www.williamlong.info/archives/4319.html "好用的Markdown编辑器一览")

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyNTU5NTg2NF19
-->