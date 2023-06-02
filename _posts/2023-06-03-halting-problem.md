---
layout: single
title: halting-problem
categories: Computer science
---

# 정지 문제

정지 문제는 판정 문제의 일종으로, 다음과 같다. 

"프로그램과 입력이 주어졌을 때, 이 프로그램이 정지한다면 True를, 정지하지 않고 영원히 계속 계산한다면 False를 반환하라."

예를 들어, 다음과 같은 함수가 주어졌다고 해보자.

어떤 프로그램이든 정지할지, 영원히 정지하지 않을지를 판정해주는 함수 halt가 존재한다고 가정하자.

```py
def halt(program, *args):
    if program(*args) is halt:
        return True
    else:
        return False
```

그리고 다음과 같은 함수가 주어졌다고 하자.

```py
def add(a, b):
    return a + b 
```

그렇다면, add(1, 2)는 정지하고, 3을 반환하기 때문에 halt(add, 1, 2)는 True를 반환할 것이다.

반면 다음과 같은 함수가 주어졌다고 하자.

```py
def func():
    while True:
        pass
```

위 함수를 실행하게 되면 무한루프에 진입하게 되고 영원히 끝나지 않는다.

그렇다면 halt(func)는 False를 반환한다는 것을 알 수 있다.

이러한 함수가 중요한 이유는 불완전성 정리와 관련이 있다.
요약하자면, 이러한 함수가 존재한다면 수학의 형식체계 자체의 무모순성을 증명할 수 있다.

자, 이제 이러한 함수가 존재하는지 증명해보자. 증명은 귀류법으로 이루어진다.

다음과 같은 함수를 정의하자.

```py
def func(program):
    if halt(program, program) == False:
        return True
    else:
        while True:
            pass
```

즉, 함수와 함수 자신이 입력으로 주어진다. (프로그램도 컴퓨터 내부에선 이진수로 존재하기 때문에 당연히 가능하다.)

그렇다면 이 함수에 자신을 인자로 넘겨보자.

```py
func(func)
```

이제 이 함수가 정지할 경우와 정지하지 않을 경우를 확인해보자.

- **func(func)가 정지하는 경우**

    이 함수가 정지한다면 halt(func, func)는 True를 반환할 것이다. 그렇다면 무한루프에 진입하게 된다. 즉, func(func)는 무한루프에 진입한다. 
    
    하지만 halt(func, func)는 True를 반환했다. 즉, 정지한다고 답했다. 이는 모순이다.

- **func(func)가 정지하지 않는 경우**

    이제 반대로 func(func)가 정지하지 않는다고 해보자.

    그렇다면 halt(func, func)는 False를 반환한다. 그리고 func(func)는 True를 반환한다.

    여기서 문제가 생긴다. halt(func, func)는 False를 반환했다. 즉, func(func)는 어떤 무한루프에 진입한다. 이는 모순이다.

이는 func 함수가 참도, 거짓도 될 수 없다는 것이므로, 모순이 발생한다.

그리고 func 함수는 halt 함수가 존재한다는 전제가 있을 때에만 정의할 수 있기 때문에, 전제가 붕괴되며, halt 함수는 존재하지 않는다는 정리로 증명이 끝난다.