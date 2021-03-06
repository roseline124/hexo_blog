---
layout: post
title:  "[백준 알고리즘#10866] 덱(Deque) 구현하기 
"
date: 2019-03-18 06:04:59
author: Roseline Song
categories: Algorithm
tags: 자료구조 알고리즘 덱 Deque
cover: "/assets/dailystudy.jpg"
---

### 백준 알고리즘 10866번
<br>


정수를 저장하는 덱(Deque)를 구현한 다음, 입력으로 주어지는 명령을 처리하는 프로그램을 작성하시오.
명령은 총 여덟 가지이다.

- push_front X: 정수 X를 덱의 앞에 넣는다.

- push_back X: 정수 X를 덱의 뒤에 넣는다.

- pop_front: 덱의 가장 앞에 있는 수를 빼고, 그 수를 출력한다. 만약, 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.

- pop_back: 덱의 가장 뒤에 있는 수를 빼고, 그 수를 출력한다. 만약, 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.

- size: 덱에 들어있는 정수의 개수를 출력한다.

- empty: 덱이 비어있으면 1을, 아니면 0을 출력한다.

- front: 덱의 가장 앞에 있는 정수를 출력한다. 만약 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.

- back: 덱의 가장 뒤에 있는 정수를 출력한다. 만약 덱에 들어있는 정수가 없는 경우에는 -1을 출력한다.

첫째 줄에 주어지는 명령의 수 N (1 ≤ N ≤ 10,000)이 주어진다. 둘째 줄부터 N개의 줄에는 명령이 하나씩 주어진다. 주어지는 정수는 1보다 크거나 같고, 100,000보다 작거나 같다. 문제에 나와있지 않은 명령이 주어지는 경우는 없다.

출력해야하는 명령이 주어질 때마다, 한 줄에 하나씩 출력한다.

<br>

### 풀이(Python)

<br>

**배운 것** : Python에서는 Switch문이 없어 Dictionary로 대신한다.

<br>

**명령어 구현**
```
def push_front(x, deq):
    tmp = [x]
    tmp.extend(deq)
    deq = tmp
    return deq

def push_back(x, deq):
    deq.append(x)
    return deq

def pop_front(deq):
    if deq : 
        print(deq.pop(0))
    else : #빈 리스트 == False
        print(-1)
    
def pop_back(deq):
    if deq :
        print(deq.pop())
    else :
        print(-1)

def size(deq):
    print(len(deq))

def empty(deq) :
    if not deq : 
        print(1)
    else : 
        print(0)
    
def front(deq) :
    if deq :
        print(deq[0])
    else :
        print(-1)
    
def back(deq) :
    if deq :
        print(deq[-1])
    else :
        print(-1)

```

<br>


**명령어 사전**
```
statements_dict = {
    'push_front' : push_front,
    'push_back' : push_back,
    'pop_front' : pop_front,
    'pop_back' : pop_back,
    'size' : size,
    'empty' : empty, 
    'front' : front,
    'back' : back
}
```

<br>

**명령어 처리**
```

N = int(input())

deq = []

for _ in range(N) :
    statement = input().split(" ")
    
    if len(statement) == 1 : 
        command = statement[0]
        statements_dict[command](deq)
    else :
        command, x = statement
        deq = statements_dict[command](x, deq)

```
