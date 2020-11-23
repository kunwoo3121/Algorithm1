# Dynamic Programming
* 동적 계획법은 크게 두가지의 방법으로 문제를 해결한다. 
1) 그 전까지의 값을 이용하여 다음의 값을 구하는 상향식 방법  
2) 연산의 결과를 저장해두는 cache 배열을 이용하여 문제를 해결하는 방법

## Floyd's Algorithm
* 플로이드 알고리즘은 가장 짧은 경로를 찾을 때 사용이 된다.
* 조건은 negative weight cycle이 없어야 한다는 것이다.
```
1) 그래프의 상태를 2차원 배열 W로 저장해둔다.
2) D[i][j]는 i정점에서 j정점으로 가는 최단 경로를 의미한다.
3) 배열 D의 값은 아래와 같은 식에 의해서 저장해나간다.
   D(k)[i][j] = { 정점1, 정점2, ... 정점k } 에 속하는 정점만 지나 정점 i 에서 정점 j 로 가는 최단 경로의 길이
   D(0) = W, D(n) = D 가 된다.
```
ex)
![KakaoTalk_20201124_004428092](https://user-images.githubusercontent.com/28796089/99982848-6ed74480-2dee-11eb-9b6d-8271f789fcf0.jpg)
D(0)[2][5] = ∞  
D(1)[2][5] = min( length{v2, v5}, length{v2, v1, v5} ) = 14  
D(2)[2][5] = D(1)[2][5] = 14  
D(3)[2][5] = D(2)[2][5] = 14  
D(4)[2][5] = min ( length{v2, v1, v5}, length{v2, v4, v5}, length{v2, v1, v4, v5}, length{v2, v3, v4, v5} ) = 5  
D(5)[2][5] = D(4)[2][5] = 5  
  
따라서 v2에서 v5로 가는 최단 경로는 5가 된다.

* D(0)에서 D(n)을 구하는 방법만 알면 된다.
```
k = 1에서 k = n 까지 상향식 방법으로 배열의 값을 채운다.
D(k)[i][j] = Min( D(k-1)[i][j],  D(k-1)[i][k] + D(k-1)[k][j] )
```

위의 방법대로 배열 D를 구해본다.

1) k = 0 
![0](https://user-images.githubusercontent.com/28796089/99987701-215dd600-2df4-11eb-8ecf-727fbcab0d55.jpg)

2) k = 1
![1](https://user-images.githubusercontent.com/28796089/99987730-29b61100-2df4-11eb-8381-e7a124146f57.jpg)

3) k = 2
![2](https://user-images.githubusercontent.com/28796089/99987762-30dd1f00-2df4-11eb-803d-a4dda36ffe33.jpg)

4) k = 3
![3](https://user-images.githubusercontent.com/28796089/99987802-389cc380-2df4-11eb-9a82-4d4bce12407a.jpg)

5) k = 4
![4](https://user-images.githubusercontent.com/28796089/99987817-3fc3d180-2df4-11eb-94e6-9ea0c7f74062.jpg)

6) k = 5
![5](https://user-images.githubusercontent.com/28796089/99987835-45b9b280-2df4-11eb-94e0-1f5e64c49f21.jpg)

k = 5 일때의 D[i][j] 가 vi ~ vj로 가는 최단 경로가 된다.
