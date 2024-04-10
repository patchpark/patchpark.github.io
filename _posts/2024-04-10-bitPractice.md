---
title: bitPractice[java]
date: 2024-04-10 20:30 +09:00
categories: [알고리즘, 비트마스킹]
---
# 문제 링크
[11723 집합](https://www.acmicpc.net/problem/11723)

# 접근 방법
이전에 풀었던 문제였다.

[11723 집합]https://patchpark.github.io/posts/11723

다시 푼 코드를 대신 기본적인 비트 연산에 대한 연습을 기록하였다.

# 문제 풀이
```java

public class Main {

	public static void main(String[] args) {		
		
		System.out.println(4 << 3);
		// 4는 이진수로 100이다 이를 3만큼 왼쪽으로 쉬프트 연산하면
		// 100000 임으로 십진수로 32임으로 32가 출력
		
		System.out.println(15 >> 1);
		// 15는 이진수로 1111이다. 이를 1만큼 오른쪽으로 쉬프트 연산하면
		// 111 임으로 십진수로 7임으로 7 출력
		
		
		System.out.println(3 | (5 << 1));
		// 3은 이진수로 11이다. 5는 이진수로 101이고 왼쪽으로 쉬프트 연산하면
		// 1010이다. 11과 1010에 OR 연산을 수행하면 1011이고 십진수로 11임으로 11 출력
		
		System.out.println(3 & (5 << 1));
		// 3은 이진수로 11이다. 5는 이진수로 101이고 왼쪽으로 쉬프트 연산하면
		// 1010이다. 11과 1010에 AND 연산을 수행하면 10이고 십진수로 2임으로 2 출력
		
		System.out.println(3 ^ (5 << 1));
		// 3은 이진수로 11이다. 5는 이진수로 101이고 왼쪽으로 쉬프트 연산하면
		// 1010이다. 11과 1010에 XOR 연산을 수행하면 1001이고 십진수로 9임으로 9 출력
		
		System.out.println(~(5 << 1));
		// 5는 이진수로 101이고 왼쪽으로 쉬프트 연산하면 1010이다.
		// NOT 연산을 수행하면 0101이고 이는 보수 연산으로 -11 출력
		
		System.out.println(Integer.toBinaryString(15));
		// 십진수 15를 이진수 1111으로 변환
		
		System.out.println(Integer.parseInt("1010", 2));
		// 이진수 1010를 십진수 10으로 변환
		
		System.out.println(Integer.parseInt("AA", 16));
		// 16진수 AA를 십진수 170으로 변환(10 * 16 + 10)
	}
	
}
```
# 출력
![bitPractice](https://github.com/patchpark/patchpark.github.io/assets/116805893/8d0ae6b5-5f71-4529-a31e-67416d5a132f)
