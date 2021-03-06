---
layout: post
title:  "[Django 스터디 준비#3-1] Model 준비 - 데이터 베이스 정규화
"
date: 2019-03-13 19:30:59
author: Roseline Song
categories: Django
tags: python django
cover: "/assets/django.jpg"
---

### 데이터베이스 정규화 공부 

Model을 디자인 하기 전, 데이터 베이스 정규화가 필요한 이유와 데이터 베이스 정규화 방법을 알아보았다. 

※참고 
- [데이터베이스 정규화가 필요한 이유](https://yaboong.github.io/database/2018/03/09/database-anomaly-and-functional-dependency/)
- [데이터베이스 정규화 방법](https://yaboong.github.io/database/2018/03/09/database-normalization-1/)

<br>
<br>

<hr>

<br>


### 데이터 추상화의 개념

현실 세계를 프로그래밍의 세계로 가져올 때 추상화를 거친다. (모델링)

예를 들어, 대학생을 추상화할 때는 학번, 이름, 학과, 소속 대학 등의 정보만 있으면 된다.

이외에 학생의 머리 색깔은 무엇인지, 소득이 얼마인지는 학생을 관리할 때 필요하지 않다.

이렇게 현실 세계의 문제를 다룰 때 필요한 정보만 고르는 것을 추상화라고 한다.

<br>
<br>

<hr>

<br>

### 데이터베이스 함수적 종속 

- X -> Y 의 관계 
- X : 결정자 / 결정자 X는 항상 고유키나 후보키에 속할 필요 없다. 
- Y : 종속자

<br>
<br>

<hr>

<br>

### 데이터베이스 정규화 

**1NF** 

하나의 컬럼에는 하나의 값만.
릴레이션에 속한 모든 속성의 도메인이 원자 값으로만 구성

<br>
<br>

**2NF**

기본키가 아닌 모든 속성이 기본키에 완전 함수 종속

즉, 결정자 집합을 구성하는 컬럼들 중 일부 컬럼이 별개로 결정자 역할을 하고 있다면 이를 제거해주는 게 2NF이다.

어떻게 제거? 다른 테이블로 분리시킨다. 

<br>
<br>

**3NF**

- 이행적 함수적 종속 : 삼단 논법과 같은 관계이다. 하지만 삼단 논법처럼 논리적인 것이 아니다.

- 학번 -> 학부 
- 학부 -> 등록금 
- 학번 -> 등록금

위와 같은 관계가 있을 때 학번은 학부를 결정 짓고, 학부는 등록금을 결정지을 수 있지만, 등록금이 학번에 의해 좌우되지는 않는다. 

이행적 종속 관계를 나타내는 컬럼들이 있다면 두 모델로 분리한다. 

위의 학번, 학부, 등록금 관계를 예로 들면, [학번, 학부], [학부, 등록금]으로 분리해야 한다. 

<br>
<br>