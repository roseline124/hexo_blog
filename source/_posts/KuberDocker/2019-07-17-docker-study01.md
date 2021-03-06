---
layout: post
title:  "[도커 스터디#1] 도커의 컨테이너, 이미지"
date: 2019-07-17 16:23:00
author: Roseline Song
categories: KuberDocker
tags: 도커 스터디
cover: "/assets/docker.jpg"
published: false
---

### 도커(Docker)란?

도커는 서버에서 여러 개의 이미지를 실행한다. 이미지 생성, 실행뿐 아니라 저장, 배포한다. 


<br>
<br>

<hr>

<br>

### 이미지 

현실 세계에서 컨테이너에 물건을 싣는 것처럼 서비스 운영에 필요한 모든 요소를 모아 Docker 컨테이너에 넣는다. 

이미지 파일에서는 어떤 운영체제, 웹서버를 사용할지 설정할 수 있다. 이미지 파일을 실행하면 설정에 따라 필요한 실행 프로그램, 라이브러리를 컨테이너에 다운 받는다.  

<br>
<br>


**1. 베이스 이미지**

리눅스 배포판의 \*유저랜드만 설치된 파일이다. 보통 리눅스 배포판의 이름으로 되어있다. 또는 유저랜드에 Redis나 Nginx가 설치된 베이스 이미지도 있다. 

<sub>
※ 유저랜드(Userland) : 운영체제의 메모리 공간 중 유저 공간은 사용자 모드 응용 프로그램이 동작하는 영역이다. 유저랜드는 이 공간에서 실행되는 프로그램 및 라이브러리를 가리킨다. 
</sub>

<br>
<br>

**2. 도커 이미지**

베이스 이미지에, 서비스 운영에 필요한 프로그램과 라이브러리 및 소스를 설치하여 하나의 파일로 만든 것이다.

<br>
<br>

**3. 도커 이미지의 동작**

이미지를 통째로 생성하는 게 아니라 바뀐 부분만 생성하여, 부모 이미지를 계속 참조한다. 


<br>
<br>

<hr>

<br>

### 컨테이너

도커의 이미지를 실행한 상태이다. `docker run 이미지태그명` 명령어를 실행하면 컨테이너를 띄울 수 있다. 운영체제에 빗대면 이미지는 실행 파일이고 컨테이너는 프로세스(실행 중인 프로그램)이다.


<br>
<br>

<hr>

<br>

### 출처

- [가장 빨리 만나는 도커](http://www.pyrasis.com/book/DockerForTheReallyImpatient/Chapter01/02)
- [유저랜드란?](https://dololak.tistory.com/353)

<br>
<br>
