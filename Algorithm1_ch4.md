# Greedy Approach
* 그 상황에서 가장 좋은 경우를 고르는 방법
* Greedy Approach로 문제를 해결할 때는 그 상황에서 최선의 선택을 하는게 최종적으로 최적의 해를 구하는 지 증명해야한다.

# Minimum Spanning Trees (MST)
* 그래프에서 모든 정점이 연결되게 하면서 간선의 가중치의 합을 가능한 최소로 하는 트리를 만든다.
* 트리는 cycle이 없는 그래프이다.

## Prim's Algorithm
* MST를 만드는 방법 중 하나
```
1) Y를 선택된 정점의 집합, V-Y를 선택해야 할 정점의 집합으로 둔다.
2) Y에서 V-Y로 가는 간선 중에서 가장 작은 가중치의 간선을 선택한다.
3) V-Y가 공집합이 될 때까지 위의 과정을 반복한다.
```
ex)
![KakaoTalk_20201124_015044421](https://user-images.githubusercontent.com/28796089/99990851-ac8c9b00-2df7-11eb-9919-d37d097e92b1.jpg)

## Kruskal's Algorithm
* MST를 만드는 방법 중 하나
```
1) 간선을 가중치가 작은 것부터 정렬한다.
2) Disjoint Set 을 만든다.
3) 정렬된 순서대로 간선을 선택한다.
4) 선택한 간선이 cycle을 만드는지 체크한다.
5) n개의 정점이 있을 때 n-1개의 간선이 선택될 때까지 위의 과정을 반복한다.
```
ex)
![1](https://user-images.githubusercontent.com/28796089/99992493-c16a2e00-2df9-11eb-91bf-7911f5f790d6.jpg)   
![2](https://user-images.githubusercontent.com/28796089/99992498-c333f180-2df9-11eb-941b-b5f298e65184.jpg)

# Dijkstra's Algorithm
* 최단경로를 구하는 알고리즘
* Floyd는 모든 정점간의 최단 경로를 구하지만 Dijkstra는 특정 정점에서 다른 모든 정점간의 최단 경로를 구할 때 쓴다.
* 간선들의 가중치는 모두 양수여야한다.
```
1) Y를 선택된 정점의 집합, V-Y를 선택해야 할 정점의 집합으로 둔다.
2) 처음에 Y에 vi를 넣고 Y에서 V-Y로 가는 가장 작은 가중치의 간선을 선택한다.
   간선의 가중치를 계산할 때 Y 내부에서의 간선의 가중치도 합해야한다.
3) V-Y가 공집합이 될 때까지 위의 과정을 반복한다.
```
ex)
![KakaoTalk_20201124_022805625](https://user-images.githubusercontent.com/28796089/99994789-d4323200-2dfc-11eb-9bef-053db55b5768.jpg)  
위와 같은 순서로 특정 정점에서 다른 모든 정점간의 최단 경로를 구한다.

