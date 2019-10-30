---
title: 알고리즘 <br/> ( MST Kruskal)
layout: post
summary: 최소비용 신장트리
categories: 
    - algorithm
    - JAVA
tags: 
   - difficulty-low: "난이도 중"
thumbnail: posts/icon-algorithm.png
pre: "/algorithm/java/2019/10/30/search-2-dfs.html"
nex: ""
---
### 1. Spanning Tree란 (신장 트리)
 - 원래의 그래프에서 모든 노드를 포함하고
 - 모든 노드들은 서로 서로 갈 수 있는 길이 있어야 하며 
 - 부모와 자식관계를 만족하는 즉 부모노드에서 자식 노드까지 가는 길이 1개만 존재할 때의 그래프를 신장트리라고 한다.
 - 아래 그림 참조(https://ratsgo.github.io 에서 퍼옴)
 - 아래 원본그래프에서 Spanning Tree는 총 8개가 존재한다.
 - N개의 정점은 N-1개의 간선으로 연결되어있다.

<div class="img-center">
    <img src="/assets/img/posts/dataStructure/spanningTree.png" class="max-ratio-100" />
</div>


### 2. MST(Minimum Spanning Tree) 최소비용 신장트리란 
 - 간선간의 비용이 주어졌을때, Spanning Tree중 최소비용을 이루는 Spanning Tree이다.

### 3.Kruskal의 MST 알고리즘
 - 탐욕적인 방법을 이용하여  모든 정점간의 비용을 연결하는 최적해답을 찾는다.

<p class="bold-text"> i) 과정</p>
 - 모든 간선들의 가중치의 오름차순으로 정렬 ( 우선순위 Que이용 )
 - pop()을 통해 가장 작은 비용의 간선 선택
 - Union-Find알고리즘으로 사이클 여부 확인 사이클이 아닐 경우 시작과 끝 노드를 union결합 후 비용을 더한다.
 - 우선순위 큐가 빌 떄 까지 계속한다. 

<p class="bold-text"> ii) 장점 </p>
   
<p class="bold-text"> iii) 단점 </p>

<p class="bold-text"> vi) 시간복잡도</p>


<p class="bold-text">i) Union-Find 알고리즘이란 </p>
 - Disjoint Set의 자료구조를 표현하기 위해 사용되는 알고리즘
 - Disjoint Set이란 서로소 집합 자료구조이다. 특정 연결이 이전 연결의 부분집합이면 안된다.
 - union( x , y) : x가 속한 집합과 y가 속한 집합을 합친다.
 - find(x) : x가 속한 집합의 대표 값을 반환한다.( root )

<p class="bold-text"> i) 과정</p>
 - Node의 갯수 만큼 data&#91;]배열을 준비하고 각 Node 숫자로 초기화
 - Union( x, y )  x<-y를 연결 시키는 경우 find(x)의 root와 , find(y)의 root를 확인 후 같은 root가 아닌 경우  find(x) <- find(y) 시킨다. 
 - find(x)는 reusult&#91;x]가 자기 자신인 경우만 root이고 아닌 경우는 연결된 경우기 때문에 find( result&#91;x] )로 무한 반복문을 돌린다.

<pre>
</pre>