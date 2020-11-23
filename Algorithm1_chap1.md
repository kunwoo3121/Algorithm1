# Four very important notations

시간 복잡도를 나타내는 방법으로는 크게 4가지가 있다.

1) Big-Oh notation
* 빅 오 표기법은 g(n) ∈ O(f(n)) 이다.
  f(n)의 점근 상한이다.
```
ex) n^2 +  10n + 9은 O(n^3)에 속한다고 할 수 있다.
    하지만 O(n)에는 속하지 않는다.
```

2) Omega notation
* 빅-오메가 표기법은 g(n) ∈ Ω(f(n))이다.
  f(n)의 점근 하한이다.
```
ex) 5n^2은 Ω(n)에 속한다고 할 수 있다.
    하지만 Ω(n^3)에 속하지 않는다.
```

3) Theta notation
* 빅-세타 표기법은 g(n) ∈ Θ(f(n))d이다.
  빅 오와 빅 오메가의 교집합이다.
```
ex) 5n^2은 Θ(n^2)이다.
```

4) Small Oh notation
* 스몰 오 표기법은 g(n) ∈ o(f(n)) 이다.
  스몰 오는 (빅 오 - 오메가 오)의 집합에 포함된다.
```
ex) n ∈ o(n^2) 이지만 n 은 o(5n)에는 속하지 않는다.
```
