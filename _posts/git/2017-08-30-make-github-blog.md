---
layout: post
title: Github & Jekyll 을 이용한 블로그 만들기
categories: [git]
excerpt: ""
comments: true
share: true
tags: [Git]
date: 2017-08-30
---

## Github 블로그 만들기?

Github 를 이용해 블로그를 만드는 방법은 여러가지가 있습니다.
본 포스팅에서는 정적 페이지를 쉽게 생성할 수 있는 Jekyll 을 사용하여 블로그를 구축하는 방법과, 이를 Github 에 업로드하고 퍼블리싱 하는 방법에 대해 설명하도록 하겠습니다.

<br>

## Jekyll 이란 무엇인가?

Jekyll(지킬) 은 Markdown 형식의 텍스트를 HTML 코드로 변환해주는 도구입니다. 사용자는 Markdown 으로 간편하게 글을 작성하면 빌드시 HTML 로 변환이 됩니다. 웹페이지를 만들 때 HTML 을 신경쓰지 않고 콘텐츠에 집중해서 글을 작성할 수 있다는 장점이 있습니다.

<br>

### 1. Jekyll 설치 (Mac 기준)

MacOS 에는 기본적으로 Ruby 가 설치되어 있습니다. 따라서 gem 명령어를 이용해 jekyll 을 바로 설치 가능합니다.

Jekyll 설치를 통해 로컬환경에서 페이지를 테스팅할 수 있습니다. 로컬에서 작업이 완료되면 git push 를 통해 원격저장소에 내용을 반영하면 됩니다.


{% highlight sh %}
$ sudo gem install jekyll
{% endhighlight %}

> 저의 경우, 설치 시 'public_suffix requires Ruby version >= 2.1.' 라는 내용과 함께 에러를 발생하였습니다. 이는 Mac 자체에 설치된 Ruby 버전이 낮을 경우 발생하며(제 경우 2.0 버전) 2.1 버전 이상으로 재설치를 해주시고 새로 설치한 버전을 Default 로 잡아주시면 됩니다.

<br>

### 2. Jekyll 프로젝트 fork 하기

Jekyll 을 이용해 제작된 많은 테마들이 http://jekyllthemes.org/ 사이트에 등록되어있습니다. 사용 방법은 큰 맥락에서 모두 동일하기 때문에 원하는 테마를 선택하시면 됩니다. 본 포스트에서는 가장 기본적이며 많이 사용되는 템플릿인 'jekyll-now' 를 적용해보도록 하겠습니다.

링크에 들어가서 fork 를 클릭합니다. (https://github.com/barryclark/jekyll-now)
![No Image](/assets/20170830/make-github-blog-01.png)

다음과 같은 화면이 나오면서 fork 가 진행됩니다.
![No Image](/assets/20170830/make-github-blog-02.png)

fork 가 완료되면 다음과 같이 자신의 Repository 에 프로젝트가 fork 된 것을 확인할 수 있습니다.
![No Image](/assets/20170830/make-github-blog-03.png)
