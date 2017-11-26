---
layout: post
title:  "파이썬으로 알고리즘 공부하기(1)"
date:   2017-11-26
description: <알고리즘 문제 풀이 전략> 예제를 풀어본다. 
---

<p class="intro"><span class="dropcap">알</span>고리즘 연습 서적인 '알고리즘 문제풀이 전략'에 있는 예제를 풀어보자. 나는 파이썬도 공부할 겸 파이썬 언어로 코드를 짜보았다.</p>

## Chapter10 - section01

###### 10진수와 16진수 변환 프로그램
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