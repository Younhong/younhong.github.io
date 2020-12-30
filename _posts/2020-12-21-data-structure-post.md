---
title: "Data Structure"
date: 2020-12-21 11:26:28 -0400
categories: Data Structure
---

# Dynamic Memory Allocation
* 정보를 저장하기 위한 메모리 공간을 확보하는 것

## Allocation
```c
int *pi = (int*)malloc(sizeof(int));
```

## Usage
```c
*pi = 1000;
```

## Release
```c
free(pi);
```

# Algorithm
* 특정한 목적을 수행하기 위한 유한한 집합의 instruction

# Data Abstraction: ADT(Abstract Data Type)
* 추상화
* 어떠한 대상의 기능만을 정의한 것, 구현 방법이나 응용 예쩨 등에 대해서는 관심이 없다.
* 예를 들어 자동차에 대한 ADT를 만든다면, 자동차의 정의와 들어가는 부품, 그리고 자동차의 기능 등이 표시되지만, 기름을 어떻게 채우는지, 자동차 내부의 내비게이션이나 라디오 시스템이 어떻게 동작하는지는 관심이 없다.

# Stack
* Ordered List where insertion/deletion is made at the top
* LIFO(Last-In-First-Out)
* Ex) Function Call

## Object
* A finite Ordered List with zero or more elements

## Operation
* Push, Pop, IsFull, IsEmpty

# Queue
* Ordered List where insertion and deletion take place at the opposite side of each other.
* FIFO(First-In-First-Out)   
* Ex) Keyboard Input, Reservation System

## Object
* A finite Ordered List with zero or more element

## Operation
* CreateQ, AddQ, DeleteQ, IsFullQ, IsEmptyQ

# Circular Quque
* Last Element Followed With First Element

# Dequeue: Double-Ended Queue
* Stack + Queue   
* 양쪽에서 모두 삽입/삭제가 가능

# Priority Queue
* 넣는 순서와 상관없이 우선순위가 높은 순서대로 빼는 Queue   
* ex) Heap

# Notation
* Infix Notation: binary operator in-between operands
> A+B

* Postfix Notation: operator after operands
> AB+   

* Prefix Notataion: operator preceding operands
> +AB

# Linked List
* Connection of nodes(elements)
* Composed of data and pointer(to next node)

* Inserting New Node(C) between A->B
1. Allocate C
2. Set Data for C
3. Link C to B
4. Link A to C

```c
Node *C = (Node *)malloc(sizeof(Node));
strcpy(C->data, "Data");
C->link = A->link;
A->link = C;
```

* Deleting Node(C) from above
1. Link A to B
2. Deallocate C

```c
A->link = C->link;
free(C);
```

# Circular Linked List
* Linked List
* Last node points first node

# Sparse Matrix
* A matrix whose non-zero elements are
sparse
* Most elements have meaningless(zero) values
* Array representation is inefficient

# Doubly Linked List
* Linked List
* Each node has two links, one to the previous node and one to the next node.

# Tree
* Hierarchial representation of a structure in a graphical form
* Set of linked nodes
1. Each node has 0 or 1 child node.
2. Child cannot have more than one parent.
3. Parent: Node without a parent.
4. Left: Node without children.

* Recursive
* Degree of a node: number of subtrees of node
> Leaf: 0 degree
* Degree of a tree: maximum degree of the node in the tree
* Sibling: 같은 부모 노드를 가진 노드들
* Path: 연결되어 있는 노드들의 순서
* Ancestors: 루트에서 노드까지 오는 path에 있는 모든 노드
* Descendents: 서브트리에 있는 모든 노드
* Level of node: 루트에서 노드까지 path에 있는 노드들의 수(root와 현재 노드도 카운트해서)
* Height/degree of a tree: maximum level of node

# Binary Tree
## Object
* Finite set of nodes
* Can have at most two children
* Children are ordered

## Operation
* create, isEmpty, makeBT, leftChild, rightChild, returnData

* Full Binary Tree
> 정의가 웹사이트별로 다르게 되어 있다. 일부는 모든 노드들이 0개 혹은 2개의 자식만을 가지는 것을 의미한다고 하지만, 다른 일부는 마지막 레벨까지 모든 노드들이 2개의 자식을 반드시 가지는 트리라고 말한다.   
> 작성자가 수강한 수업 기준으로 앞의 정의가 full binary tree의 정의에 해당되므로 여기에서는 full binary tree는 모든 노드들이(마지막 레벨의 노드 제외) 반드시 2개의 자식 노드를 갖는 꽉찬 트리라고 정의하겠다.

* Complete Binary Tree
> 이진 트리 중에서도, 위에서 아래로, 왼쪽에서 오른쪽으로 순서대로 트리의 값을 채워나가면서 마지막 노드에 이르기 전까지 모든 노드의 값은 채워져 있어야 하는 트리이다.

## Traversal
* In-order Traversal
> Left -> Current -> Right
* Pre-order Traversal
> Current -> Left -> Right
* Post-order Traversal
> Left -> Right -> Current
* Level-order Traversal
> 각 레벨별로 (왼쪽부터) 출력하면서 아래 레벨로 내려가는 방식

# Heap
* Max Tree: 부모 노드가 항상 자식 노드보다 작지 않은 값을 가지는 트리
* Max Heap: Complete Max Tree
* Min Tree: 부모 노드가 항상 자식 노드보다 크지 않은 값을 가지는 트리
* Min Heap: Complete Min Tree

* Heap: 가장 큰(혹은 작은) 값을 뽑아내거나 추가하는데 효율적인 구조
* 정렬이 되어 있는 배열이나 Linked List:
> 값을 뽑는데는 효율적이지만 추가하는데 비효율적
* 정렬이 되어 있지 않은 배열이나 Linked List:
> 값을 추가하는데 효율적이나 뽑아내는데 비효율적

* 다시 등장한 Priority Queue
>> Heap을 통해 구현

# Max Heap
## Object 
* Complete binary tree of n(>=0) elements organized so that each node is larger or equal to its children node

## Operation
* create, insert, delete, isFull, isEmpty

* Insertion
1. 노드를 가장 마지막에 추가
2. 위로 올라가면서 조건에 맞게 순서를 바꿔주는 방식

* Deletion
1. Root를 제거
2. 가장 마지막 노드를 루트에 배치
3. 자식 노드 중에 가장 큰 값이랑 교체하면서 아래로 내려감

# Binary Search Tree
* 루트에서 시작해서 아래로 내려가면서 타깃 값을 찾는 방식
* 기본적으로 트리의 값의 구조가 왼쪽 서브트리의 값이 루트보다 작으며, 오른쪽 서브트리의 값이 루트보다 커야 한다.

# Graph
* 노드와 edge의 집합
* G = (V, E)

* Directed Graph / Undirected Graph
>> edge에 order(방향) 유무

* Complete Graph
>> Max # of edge를 가진 그래프

* Subgraph
>> 그래프의 모든 e, v가 다른 그래프에 포함되는 경우에 해당된다.

* path
>> sequence of vertices connected
* simple path
>> path 안의 처음과 마지막 vertice를 제외하고 다 다른 경우
* cycle
>> simple path이고 처음과 마지막 vertice가 같은 경우

* Connected
>> 두 점 사이에 경로가 존재한다면 connected
* Connected Component
>> Maximum Connected Subgraph
* Strongly Connected Directed Component
>> 모든 점 사이에 directed path가 존재한다.
* Degreee
>> Number of edges incident to that vertex   
>> 1. In-degree / Out-degree

## Object
* Nonempty set of vertices and a set of undirected edges where each edge is a pair of vertices
## Operation
* Create, insertEdge, insertVertex, deleteVertex, deleteEdge, Adjacent, isEmpty

# Adjacency Matrix
* 행렬로 연결을 나타낸 것
* 연결되었으면 1, 아니면 0으로 표시
# Adjacency List
* Linked List로 연결된 것을 표시하는 방식

# Weighted Graph
* 각 edge들에 숫자(weight)를 할당하여 표시한 그래프

## 다시 돌아온 Traversal
* 앞의 tree traversal과 비교
* DFS(Depth first search)
> 가능한 깊게 들어가는 방식   
> pre-order traversal과 유사
* BFS(Breadth first search)
> 현재 위치에서 가까운 위치에 있는 노드들을 먼저 다 처리한 후에 이동하는 방식   
> level-order traversal과 유사

# Tree에 대한 재정의
* 두 점이 하나의 경로로만 연결된 그래프

# Spanning Tree
* 어떤 그래프의 모든 점을 다 포함하는 서브그래프

## Minimum cost of spanning tree
*  Kruskal's Algorithm
> 자세한 건 알고리즘 파트에서 이어집니다.

# Shortest Path
* Single Source All Destinations
> 어떤 한 점에서 나머지 점까지 가장 짧은 경로를 표시   
> Dijkstra's Algorithm
* All Pairs Shortest Paths
> 위의 알고리즘을 확장해 모든 점 사이의 shortest path를 찾아내는 것   
> Floyd's Algorithm

* 자세한 건 알고리즘 파트에서 더욱 자세히 다룹니다

# Sequential Search
* 앞에부터 순서대로 가면서 찾는 방식

# Binary Search
* 배열을 순서대로 정렬
* 중간부터 목표 값과 비교하며 값을 찾아나가는 방식

# Insertion Sort
* 리스트에서 앞에서부터 순서대로 값을 뽑아서, 정렬된 리스트에 하나씩 넣는다.

# Quick Sort
* pivot 값을 선택한다.
* 리스트를 pivot보다 작은 값, pivot, pivot보다 큰 값 순서대로 넣는다.
* 모든 리스트가 정렬될 때까지 반복

# Merge Sort
* 두 개의 sorted list를 merge

# Heap Sort
* 정렬되지 않은 리스트로부터 max heap을 만드는 소팅 알고리즘

# Radix Sort
* 가장 중요한 digit부터 덜 중요한 digit 순서대로 정렬하는 방식

# Symbol Table
## Object
* Set of name-attribute pairs(unique namemm)

## Operation
* Create, Find, isIn, Insert, Delete

# Hashing
* Symbol table보다 더 효율적인 방법

# Static Hashing
## Hash table
* 식별자를 저장하기 위한 테이블

## Hash function
* 식별자의 주소를 매핑하는 함수

### Overflow Handling
* Linear Probing
> 버킷이 다 차면 다음 버킷에 값을 저장한다.

## 단점
* 메모리 소모량

* Chaining
> 버킷을 Linked List로 저장

# Dynamic Hashing
## Trie
*  이진 트리
* 식별자를 bit sequenceㅇ 따라 배치시킨다.

### Overflow Handling
* 새로운 페이지를 추가해서 depth를 늘린다.