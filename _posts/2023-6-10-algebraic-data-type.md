---
layout: single
title: "대수적 데이터 타입"
categories: computer-science
tag: [mathematics, computer-science]
use_math: true
---

대수적 데이터 타입은 프로그래밍 언어에서 다양한 데이터 유형을 나타내는 방법중 하나이다.

즉, 대수적 데이터 타입을 통해서 더욱 다양한 데이터들을 표현하고, 다룰 수 있다.

대수적 데이터 타입은 일반적으로 크게 두 가지 형태로 구성된다. 바로 합타입과 곱타입이다.

- 합타입(Sum type): 자바에선 대표적으로 Enum이 있다. 합타입은 수학에선 마치 합집합과 같은 것이다.(정확히는 분리 합집합과 같다. 범주론에서는 이를 쌍대곱으로 일반화한다.) $\frac{a:A \ \ a:B}{a:A+B}$
- 곱타입(Product type): 대표적으로 클래스가 있다. 튜플, 리스트, 그래프등이 여기에 해당한다. 집합론에선 곱집합과 같다.(범주론에선 곱범주를 통해 일반화한다. 곱범주의 쌍대가 쌍대곱이다. 즉, 서로 반대 개념이다.) $\frac{a:A \ \ b:B}{[a, b]: A\times B}$

위 사실에서 알 수 있듯, 수학은 알고리즘뿐만 아니라, 데이터 구조에서도 이론적 기반을 제공해준다.

# 범주론적 정의

<img src="https://i.upmath.me/svg/%0A%5C%5B%5Cbegin%7Btikzcd%7D%0A%09%26%20%5Ctextcolor%7Bwhite%7D%7BX%7D%20%5C%5C%0A%09%5Ctextcolor%7Bwhite%7D%7BY%7D%20%26%20%5Ctextcolor%7Bwhite%7D%7BX_i%7D%0A%09%5Carrow%5B%22%7Bf_i%7D%22'%2C%20color%3Dwhite%2C%20from%3D2-1%2C%20to%3D2-2%5D%0A%09%5Carrow%5B%22f%22%2C%20color%3Dwhite%2C%20dashed%2C%20from%3D2-1%2C%20to%3D1-2%5D%0A%09%5Carrow%5B%22%7B%5Cpi%20_i%7D%22%2C%20color%3Dwhite%2C%20from%3D1-2%2C%20to%3D2-2%5D%0A%5Cend%7Btikzcd%7D%5C%5D%0A" alt="
\[\begin{tikzcd}
	&amp; \textcolor{white}{X} \\
	\textcolor{white}{Y} &amp; \textcolor{white}{X_i}
	\arrow[&quot;{f_i}&quot;', color=white, from=2-1, to=2-2]
	\arrow[&quot;f&quot;, color=white, dashed, from=2-1, to=1-2]
	\arrow[&quot;{\pi _i}&quot;, color=white, from=1-2, to=2-2]
\end{tikzcd}\]
" />

여기서 X를 곱이라 한다.

위 범주의 쌍대범주는 쌍대곱을 일반화한 개념이다.

# Deque의 범주론적 정의

큐와 스택의 구조를 포함하는 덱은 범주론적으로 조금 특별한 구조를 갖는다.

덱은 두 범주의 개념을 동시에 만족한다.

1.
<img src="https://i.upmath.me/svg/%0A%5C%5B%5Cbegin%7Btikzcd%7D%0A%09%26%20%5Ctextcolor%7Bwhite%7D%7BX%7D%20%5C%5C%0A%09%5Ctextcolor%7Bwhite%7D%7BY%7D%20%26%20%5Ctextcolor%7Bwhite%7D%7BX_i%7D%0A%09%5Carrow%5B%22%7Bf_i%7D%22'%2C%20color%3Dwhite%2C%20from%3D2-1%2C%20to%3D2-2%5D%0A%09%5Carrow%5B%22f%22%2C%20color%3Dwhite%2C%20dashed%2C%20from%3D2-1%2C%20to%3D1-2%5D%0A%09%5Carrow%5B%22%7B%5Cpi%20_i%7D%22%2C%20color%3Dwhite%2C%20from%3D1-2%2C%20to%3D2-2%5D%0A%5Cend%7Btikzcd%7D%5C%5D%0A" alt="
\[\begin{tikzcd}
	&amp; \textcolor{white}{X} \\
	\textcolor{white}{Y} &amp; \textcolor{white}{X_i}
	\arrow[&quot;{f_i}&quot;', color=white, from=2-1, to=2-2]
	\arrow[&quot;f&quot;, color=white, dashed, from=2-1, to=1-2]
	\arrow[&quot;{\pi _i}&quot;, color=white, from=1-2, to=2-2]
\end{tikzcd}\]
" />

2.
<img src="https://i.upmath.me/svg/%5C%5B%5Cbegin%7Btikzcd%7D%0A%09%5Ctextcolor%7Bwhite%7D%7BS_A%5Cotimes%20A%7D%20%26%26%20%5Ctextcolor%7Bwhite%7D%7BS_A%5Cotimes%20A%2BI%7D%20%5C%5C%0A%09%26%20%5Ctextcolor%7Bwhite%7D%7BS_A%7D%20%26%26%20%5Ctextcolor%7Bwhite%7D%7BS_A%2BI%7D%0A%09%5Carrow%5B%22%7Bpush_A%7D%22'%2C%20color%3Dwhite%2C%20from%3D1-1%2C%20to%3D2-2%5D%0A%09%5Carrow%5B%22%7Bpop_A%7D%22'%2C%20color%3Dwhite%2C%20from%3D2-2%2C%20to%3D1-3%5D%0A%09%5Carrow%5B%22%7Bpush_A%2Bid_I%7D%22%2C%20color%3Dwhite%2C%20from%3D1-3%2C%20to%3D2-4%5D%0A%09%5Carrow%5B%22%7B%5Ciota_%7BS_A%5Cotimes%20A%2CI%7D%7D%22%2C%20color%3Dwhite%2C%20from%3D1-1%2C%20to%3D1-3%5D%0A%09%5Carrow%5B%22%7B%5Ciota_%7BS_A%5Cotimes%20A%2CI%7D%7D%22'%2C%20color%3Dwhite%2C%20from%3D2-2%2C%20to%3D2-4%5D%0A%5Cend%7Btikzcd%7D%5C%5D" alt="\[\begin{tikzcd}
	\textcolor{white}{S_A\otimes A} &amp;&amp; \textcolor{white}{S_A\otimes A+I} \\
	&amp; \textcolor{white}{S_A} &amp;&amp; \textcolor{white}{S_A+I}
	\arrow[&quot;{push_A}&quot;', color=white, from=1-1, to=2-2]
	\arrow[&quot;{pop_A}&quot;', color=white, from=2-2, to=1-3]
	\arrow[&quot;{push_A+id_I}&quot;, color=white, from=1-3, to=2-4]
	\arrow[&quot;{\iota_{S_A\otimes A,I}}&quot;, color=white, from=1-1, to=1-3]
	\arrow[&quot;{\iota_{S_A\otimes A,I}}&quot;', color=white, from=2-2, to=2-4]
\end{tikzcd}\]" />

# 불필요한 엄밀성

위와 같은 어려운 수학적 개념을 프로그래밍에 동원할 필요성을 느끼는 사람도 있을 것이다.

이는 마치 수리 물리학에 비유할 수 있다. 수리 물리학은 이론 물리학에서는 불필요한 수학적 엄밀성과 체계성까지 고려한다. 하지만 그러한 노력을 통해서 더욱 풍부한 개념과 활용성을 가져갈 수 있다.

쉽게 예를 들어본다면, 이분탐색 알고리즘은 잘 "정렬된" 구조 위에서 어떠한 값을 찾는 알고리즘이다.
즉, 수학적으로 순서관계 위에서 어떠한 값을 찾는 알고리즘으로 간주할 수 있다.

순서관계만 잘 주어져 있다면, 이분탐색 알고리즘을 사용할 수 있다는 뜻이다.

보통이라면 배열에서 이를 수행하겠지만 더 확장해서 n차원 배열에서도 적용할 수 있다.(당연하다.)
뿐만 아니라 그래프등에도 응용할 수 있다.

수학을 통해 더 넓은 통찰력과 사고력을 기를 수 있다.

**컴퓨터 과학은 수학에 기초한 과학의 한 분야라는 것을 잊지말자.**