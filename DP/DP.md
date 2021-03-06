# 다이나믹 프로그래밍(Dynamic Programming)

```
  다이나믹 프로그래밍은 기존의 프로그래밍 방식으로 풀기 쉽지 않은 문제들을
  TOP-DOWN 혹은 BOTTOM-UP 방식을 사용하여 메모리 공간을 조금더 사용하지만 
  풀릴 수 있도록 하는 알고리즘이다.
  
  이전 절차의 알고리즘과 쌓여있는 이전 데이터를 사용하면 현재 절차의 답이 나오는
  알고리즘이다.
```

## 예시
```
  DP의 가장 유명한 예는 피보나치 함수문제이다.
  피보나치 문제를 현재 절차 이전의 절차와 같은 알고리즘을 사용하면 문제가 풀린다. 
  수학의 점화식과 같은 개념이다.
  
  이러한 DP 방식의 풀이법은 크게 2가지로 나뉠 수 있다.
  TOP-DOWN, BOTTOM-UP 방식이다.
```

### TOP-DOWN
 - top-down 방식은 재귀 함수를 통해 가장 위 루트 노드부터 재귀를 시작한다.
 - 재귀는 중복 재귀를 불러 효율성에 문제를 일으킨다.
 - 중복재귀를 막기 위해 메모이제이션 방법을 사용한다.
 ```python
  dy = [0] * 100
  def fibo(x):
      if x == 1 or x == 2:
          return 1

      # 이미 한번 방문했던 재귀일 경우(메모이제이션)
      if dy[x] != 0:
          return dy[x]

      dy[x] = fibo(x-1) + fibo(x-2)

      return dy[x]

 ```
 
 ### BOTTOM-UP
  - bottom-up 방식은 top-down 방식과 다르게 반복문을 사용하여 dp를 풀어낸다.
  - dp 문제는 보통 bottom-up 방식을 사용해 푼다.
  ```python
  dy[1] = 1
  dy[2] = 1
  n = 99

  for i in range(3, n+1):
      dy[i] = dy[i-1] + dy[i-2]
```
