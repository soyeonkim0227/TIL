## 큐(Queue) 정의

---

<aside>
🧷 deque 자료형으로 popleft()하는 게 훨씬 효율적이다. O(1)
먼저 들어온 데이터가 먼저 나가는 구조 - 선입선출(FIFO: First-In First-Out)

</aside>

## Queue의 구조

---

![image](https://user-images.githubusercontent.com/102784901/232233416-15abc597-9456-4eb1-855b-efbffb0a17fe.png)

![image](https://user-images.githubusercontent.com/102784901/232233458-124ed1a3-ca85-4d1c-8b88-42070fc32baa.png)


- 삽입이 일어나는 곳: rear, 삭제가 일어나는 곳: front

## Queue 기본연산

---

- **add(item)**
item을 리스트의 끝부분에 추가함.
- **remove()**
리스트의 첫 번째 항목을 제거함.

## Queue 리스트 함수로 구현

---

```python
queue = list()

queue.append(0) # 요소 0 추가
queue.append(1) # 요소 1 추가
queue.append(2) # 요소 2 추가

del queue[0] # 요소 0 제거
queue.pop(0) # 요소 1 제거

print(queue) # 2
```

```python
>>> queue = [4, 5, 6]
>>> queue.insert(0, 3)
>>> queue.insert(0, 2)
>>> queue
[2, 3, 4, 5, 6]
>>> queue.pop()
6
>>> queue.pop()
5
>>> queue
[2, 3, 4]
```

- 요소를 추가할 때는 `append(a)`, 삭제할 때는 `del` 키워드나 `pop()` 함수를 사용함.
- 파이썬의 list는 다른 언어의 배열처럼 무작위 접근(random access)에 최적화된 자료 구조이기 때문에 pop(0) 또는 insert(0, x)는 성능적으로 매우 불리한 연산임.
- 이 두 연산의 시간 복잡도는 O(n)이기 때문에 담고 있는 데이터의 개수가 많아질 수록 느려짐.
- 왜냐하면 첫 번째 데이터를 제거한 후에는 그 뒤에 있는 모든 데이터를 앞으로 한 칸씩 당겨줘야 하고, 맨 앞에서 데이터를 삽입하려면 그 전에 모든 데이터를 뒤로 한 칸씩 밀어줘야 하기 때문임.

## Queue 시간복잡도

---

- `front`, `rear`의 위치로 데이터 삽입 삭제가 바로 이루어지기 때문에 원소 삽입, 삭제의 시간 복잡도는 **O(1)임.**

## Queue 장단점

---

- 장점
    - 데이터 접근, 삽입, 삭제가 빠름.
- 단점
    - 큐 역시 스택과 마찬가지로 중간에 위치한 데이터에 대한 접근이 불가능함.

## Queue 활용

---

- 데이터를 입력된 순서대로 처리해야 할 때
- BFS(너비 우선 탐색, Breath First Search) 알고리즘
- 프로세스 관리
- 대기 순서 관리

## 덱(Deque) 정의

---

![image](https://user-images.githubusercontent.com/102784901/232233521-f0476c1c-ee5d-4ee1-97b4-30985f728cf7.png)

<aside>
🧷 Double-Ended Queue의 줄임말.
한쪽에서만 삽입, 다른 한쪽에서만 삭제가 가능했던 큐와 달리 양쪽 front, rear에서 삽입 삭제가 모두 가능한 큐를 의미하는 자료구조

</aside>

- 연속적인 메모리를 기반으로 하는 시퀀스 컨테이너이고 선언 이후 크기를 줄이거나 늘릴 수 있는 가변적 크기를 가짐.
- 또한, 중간에 데이터가 삽입될 때 다른 요소들을 앞, 뒤로 밀 수 있음.
- 하지만, 앞 뒤에서의 삽입 삭제 성능에 비해 중간에 삽입 삭제하는 것은 성능에 좋지 않음.

## Deque 모듈로 구현

---

```python
>>> from collections import deque
>>>
>>> queue = deque([4, 5, 6])
>>> queue.append(7)
>>> queue.append(8)
>>> queue
deque([4, 5, 6, 7, 8])
>>> queue.popleft()
4
>>> queue.popleft()
5
>>> queue
deque([6, 7, 8])
```

- `collections` 모듈의 `deque` 사용.
- `deque`는 `list`에는 없는 `popleft()`라는 메서드를 제공함.
- 이 메서드를 사용하면 첫 번째 데이터를 제거할 수 있음.
- 데이터의 흐름은 `list` 객체의 `pop(0)` 메서드를 사용할 때처럼 뒤에서 앞으로 흐르게 됨.

```python
>>> from collections import deque
>>>
>>> queue = deque([4, 5, 6])
>>> queue.appendleft(3)
>>> queue.appendleft(2)
>>> queue
deque([2, 3, 4, 5, 6])
>>> queue.pop()
6
>>> queue.pop()
5
>>> queue
deque([2, 3, 4])
```

- `deque`는 `appendleft(x)`라는 메서드도 제공함.
- 이 메서드를 사용하면 데이터를 맨 앞에서 삽입할 수 있음.
- 이 경우, 데이터의 흐름은 `list` 객체의 `insert(0, x)` 메서드를 사용할 때처럼 아펭서 뒤로 흐르게 됨.

## 모듈 구현과 list 구현

---

- `deque`의 `popleft()`와 `appendleft(x)` 메서드는 모두 `O(1)`의 시간 복잡도를 가지 때문에, 위에서 살펴 본 `list`의 `pop(0)`와 `insert(0, x)` 대비 성능 상에 **큰 이점**이 있음.
- 하지만 모든 자료구조가 그러하듯 `deque`도 단점이 존재함.
    - 바로 무작위 접근(random access)의 시간 복잡도가 `O(n)`이라는 것임.
    - 내부적으로 `linked list`를 사용하기 때문에 `i`번째 데이터에 접근하려면 맨 앞/뒤부터 `i`번 순회(iteration)가 필요하기 때문임.

## `queue` 모듈의 `Queue` 클래스 사용

---

- 주로 멀티 스레딩(threading) 환경에서 사용되며, 내부적으로 라킹(locking)을 지원하여 여러 개의 스레드가 동시에 데이터를 추가하거나 삭제할 수 있음.
- `list`나 `deque`와 달리 방향성이 없기 때문에 데이터 추가와 삭제가 하나의 메서드로 처리됨.
- 따라서, 데이터를 추가하려면 `put(x)` 메서드를 사용, 데이터를 삭제하려면 `get()` 메서드를 사용

```python
>>> from queue import Queue
>>> 
>>> que = Queue()
>>> que.put(4)
>>> que.put(5)
>>> que.put(6)
>>> que.get()
4
>>> que.get()
5
>>> que.get()
6
```

- `Queue`는 `deque`처럼 `O(1)` 데이터 추가/삭제 성능을 보임.
- `list`나 `deque`와 달리 인텍스로 데이터에 접근하는 것은 기본적으로 지원하지 않음.

## Deque 시간 복잡도

---

- 삽입 삭제 연산은 마찬가지로 **O(1)**의 시간 복잡도를 가지고, 스택/큐와 달리 index를 통해 요소들에 탐색이 가능하므로 이 역시 **O(1)**의 시간 복잡도를 가짐.

## Deque 장단점

---

- 장점
    - 데이터의 삽입 삭제가 빠르고 앞, 뒤에서 삽입 삭제가 모두 가능함.
    - 크기가 가변적임.
    - index를 통해 원하는 원소에 바로 접근이 가능함.
    - 새로운 원소 삽입 시, 메모리를 재할당하고 복사하지 않고 새로운 단위의 메모리 블록을 할당하여 삽입함.
- 단점
    - 구현이 어려움.
    - 데이터 중간의 삽입 삭제가 용이하지 않음.

## Deque 활용

---

- 덱이 자주 쓰이는 편은 아님.
- 주로 앞, 뒤 모두에서 삽입, 삭제할 때 사용
- 데이터의 크기가 가변적일 때 일반적으로 사용됨.
