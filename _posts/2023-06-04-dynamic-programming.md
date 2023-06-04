---
layout: single
title: "동적 계획법"
categories: computer-science
tag: [mathematics, computer-science]
use_math: true
---

동적 계획법은 최적화 기법중 하나이다. (알고리즘보단 기법에 가깝다.)

복잡한 문제를 여러 문제로 나누고, 풀었던 문제들을 재활용하는 것이 동적 계획법의 핵심이다.

이러한 구조를 **최적 부분 구조** 라고 부른다.

동적 계획법에서는 점화식이 핵심이다.
왜냐하면, 최적 부분 구조를 표현할 수 있는 적합한 도구가 수열이기 때문이다.

애초에 컴퓨터 과학은 다른 과학 분야와는 다르게 수학에 기초를 둔 학문이기 때문에 그리 놀라운 말은 아니다. 물리학의 경우에는 자연 현상을 정량화하고 표현하기 위해 수학을 이용할 뿐이다.

동적 계획법은 위에서 말했듯이, 복잡한 문제를 분할하고, 풀었던 문제들을 재활용하는 것이 핵심이기 때문에, 메모이제이션과도 관련이 깊다.

메모이제이션이란, 이전에 계산한 값을 메모리에 저장하여, 동일한 계산을 다시 반복하지 않도록 하여, 프로그램 실행 속도를 향상시킨다.

피보나치 수열을 예시로 들어서 설명하겠다.

피보나치 수열의 정의는 다음과 같다.

$a_0=1$

$a_1=1$

$a_n=a_{n-1}+a_{n-2} \quad (n \geq 2)$

```java
import java.util.Scanner;

public class Main {
    static int[] memo; // memoization

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        memo = new int[n];
        memo[0] = 1;
        memo[1] = 1;

        System.out.println(dynamic_fibo(n - 1));
    }

    static int dynamic_fibo(int i) { // 동적 계획법을 적용한 피보나치 수열
        if (memo[i] != 0) return memo[i];
        else {
            memo[i] = fibo(i - 1) + fibo(i - 2);
            return memo[i];
        }
    }

    static int recursion_fibo(int i) { // 피보나치 수열
        if (i == 0 || i == 1) return 1;
        else return recursion_fibo(i - 1) + recursion_fibo(i - 2);
    }
}
```

위 코드에서 실제로 두 피보나치 수열의 성능을 비교해보면 동적 계획법을 적용한 피보나치 수열의 속도가 더 빠를 것이다.

일반적인 방법으로 정의한 피보나치 수열의 시간 복잡도는 $O(2^n)$이다.

하지만 동적 계획법을 적용하게 되면 시간 복잡도는 $O(n)$이 된다.
