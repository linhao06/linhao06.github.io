---
title: Hexo Indigo theme 적용
date: 2019-01-13 01:24:03
tags: GitHub, Hexo
---

# 1. Hexo indigo theme 및 dependencies module install #

	git clone git@github.com:yscoder/hexo-theme-indigo.git themes/indigo
	npm install hexo-renderer-less --save   #安装less,作为css的预处理工具
	npm install hexo-generator-feed --save #安装rss的feed生成工具
	npm install hexo-generator-json-content --save #用于生成静态站点数据，用于站内搜索的数据源
	npm install hexo-helper-qrcode --save #用于生成微信分享二维码(Option)

## 2. Tags,Categories 페이지 생성 ##

	hexo new tags
	hexo new categories

source/tags/index.md파일에 아래내용 추가

	layout: tags
	comments: false

source/tags/categories.md파일에 아래내용 추가

	layout: categories
	comments: false

# 3. Indigo 적용 #

Root폴더 _config.yml파일에 indigo theme적용

	# Extensions
	## Plugins: https://hexo.io/plugins/
	## Themes: https://hexo.io/themes/
	theme: indigo

Hexo 실행

	hexo clean & hexo g & hexo s 

배포

	hexo d

# 4. Indigo 기본 설정 변겅 #

	/theme/indigo/_config.yml에서 속성값 변경

**Reference: **

[hexo安装、生成blog并deploy到github](https://blog.csdn.net/u010075335/article/details/82861322 "hexo安装、生成blog并deploy到github")