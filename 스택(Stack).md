## 스택(Stack) 정의

<aside>
📌 가장 나중에 넣은 데이터를 가장 먼저 빼낼 수 있는 데이터 구조 - 후입선출(LIFO: Last-in First-out)

</aside>

## Stack 기본연산

---

- **push()**
스택에 원소를 추가함.
- **pop()**
스택 가장 위에 있는 원소를 삭제하고 그 원소를 반환함.
- **peek()**
스택 가장 위에 있는 원소를 반환함. (삭제하지는 않음.)
- **empty()**
스택이 비어있다면 1, 아니면 0을 반환함.

## Stack 리스트 함수로 구현

---

```python
stack = []

# push()
stack.append(2)
stack.append(1)
stack.append(0)
stack.append(5)

print(stack) # [2, 1, 0, 5]

# pop()
stack.pop()
stack.pop()
stack.pop()

print(stack) # [2]
```

## Stack 장단점

---

- 장점
    - 구조가 단순해서 구현이 쉬움
    - top을 통해 접근하기 때문에 데이터 접근, 삽입, 삭제가 빠름.
- 단점(일반적인 스택 구현 시)
    - 데이터 최대 갯수를 미리 정해야 함.
    - 저장공간의 낭비가 발생할 수 있음. (미리 최대 갯수만큼 저장 공간을 확보해야 함.
    - top 위치 이외의 데이터에 접근할 수 없기 때문에 탐색이 불가능함. 탐색하려면 모든 데이터를 꺼내면서 진행해야 함.

## Stack 활용

---

- 재귀 알고리즘
- DFS 알고리즘
- 작업 실행 취소와 같은 역추적 작업이 필요할 때
- 괄호 검사, 후위 연산법, 문자열 역순 출력 등

## Stack의 시간 복잡도

---

- insert: O(1)
- delete: O(1)
- search: O(n)

> 삭제나 삽입 시 맨 위에 데이터를 삭제하거나 삽입하기 때문에 시간 복잡도는 늘 O(1)이다. 하지만 특정 데이터를 찾을 때는 값을 찾기위해 순회해야 하므로 O(n)의 시간 복잡도를 가짐.
> 

## Stack 라이브러리

---

- 파이썬 내장모듈에서는 따로 스택 라이브러리가 존재하진 않음.
- 보통 덱 라이브러리를 import 해서 스택 대신 사용함.

```python
from collections import deque

dq=deque() # 덱 생성
dq.append() # 덱의 가장 오른쪽에 원소 삽입
dq.popleft() # 가장 왼쪽 원소 반환
dq.appendleft() # 덱의 가장 왼쪽에 원소 삽입
dp.pop() # 가장 오른쪽 원소 반환
dp.clear() # 모든 원소 제거
dp.copy() # 덱 복사
dp.count(x) #x와 같은 원소의 개수를 계산
```
