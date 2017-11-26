---
layout: post
title:  "파이썬으로 알고리즘 공부하기(1)"
date:   2017-11-26
description: <알고리즘 문제 풀이 전략> 예제를 풀어본다. 
---

<p class="intro"><span class="dropcap">알</span>고리즘 연습 서적인 '알고리즘 문제풀이 전략'에 있는 예제를 풀어보자. 나는 파이썬도 공부할 겸 파이썬 언어로 코드를 짜보았다.</p>

## Chapter10 - section01

### 10진수와 16진수 변환 프로그램
10진수를 16진수로 변환하거나, 16진수를 10진수로 변환하는 계산기 프로그램을 작성한다.
1. a나 b 중 키 하나를 입력 받는다.
2. 변환할 수를 입력 받는다.
3. 수를 변환한다.
4. 출력한다.

{% highlight python %}
scan = input('a나 b를 누르세요 : ')
num = input('변환할 숫자를 입력하세요 : ')
if scan == 'a':
    num = int(num)
    trans = hex(num)
    print ("10진수 : ", num, " -> 16진수 : ", trans)
elif scan == 'b':
    trans = int(num, 16)
    print ("16진수 : ", num, " -> 10진수 : ", trans)
{% endhighlight %}

## Chapter10 - section02

### 숫자 맞추기 프로그램
임의의 수를 생성하고 숫자를 맞추는 프로그램을 작성한다.
1. 랜덤함수를 이용하여 숫자 하나를 생성한다. (1~100로 범위를 지정함)
2. 사용자에게 숫자를 입력받는다.
3. 맞으면 끝, 틀리면 크다/작다를 출력한다.
4. 맞출때까지 반복한다.

{% highlight python %}
import random
num = random.randrange(1,100)
print('1~100중 임의의 숫자를 생성하였습니다.')
i = 1
while i > 0:
    print (i, '번째 도전 : ')
    a = int(input())
    if a == num:
        print('맞췄어요!')
        i = -1
    elif a > num:
        print(a, '보다 작습니다.')
        i +=1
    elif a < num:
        print(a, '보다 큽니다.')
        i +=1
{% endhighlight %}

## Chapter10 - section03

### 두 수의 최대공약수 구하기
임의의 두 수를 입력받고, 두 수의 최대공약수를 구하는 프로그램을 작성한다.
유클리드 호제법을 활용하였다.
1. 사용자로부터 두 수를 입력 받는다.
2. 큰 수를 작은 수로 나눈 나머지 값을 구한다.
3. 나머지가 0일 경우, 나눈 수가 두 수의 최대공약수가 된다.
4. 나머지가 0보다 클 경우, 나눈 수를 나머지 값으로 다시 나눈다. 나머지 값이 0이 될 때까지 반복한다.

{% highlight python %}
a, b = input('두 정숫값을 입력하시오: ').split()
a = int(a)
b = int(b)
if a < b:
    t = a
    a = b
    b = t

while 1:
    r = a%b
    if r == 0:
        break
    elif r > 0:
        a = b
        b = r
print ('최대공약수는 ', b)
{% endhighlight %}