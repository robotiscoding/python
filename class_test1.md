총 10문제이며, **모두 빈칸 채우기** 문제입니다.  
일부 문제는 **클래스**(생성자, 메서드, 상속 등)를 다룹니다.  
빈칸을 채워 `solution` 호출 또는 마지막 실행 결과가 예시와 같도록 하세요.

> ※ 한 문제당 최대 5개의 빈칸이 있습니다.  

---

### 문제 1 (빈칸) – 1부터 n까지의 합 (인덱스/범위)

- **문제 설명**  
  정수 `n`이 주어질 때, 1부터 n까지의 합을 반환하는 `solution` 함수를 완성하세요. (`n`은 1 이상)

- **함수 설명**
  - 매개변수: `n` (정수)
  - 반환값: 1 + 2 + … + n (정수)

- **코드 (빈칸 채우기)**

```python
def solution(n):
    total = 0
    for i in range($blank$):
        total += i
    return total
```

- **예시 테스트케이스**
  - `5` → `15`
  - `10` → `55`
  - `1` → `1`

---

### 문제 2 (빈칸) – 리스트 마지막 k개 원소

- **문제 설명**  
  정수 리스트 `nums`와 정수 `k`가 주어질 때,  
  마지막 `k`개의 원소를 담은 리스트를 반환하는 `solution` 함수를 완성하세요.  
  `k`가 리스트 길이보다 크면 전체 리스트를 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `k` (정수)
  - 반환값: 마지막 k개 원소 리스트

- **코드 (빈칸 채우기)**

```python
def solution(nums, k):
    if k >= len(nums):
        return nums[$blank$]
    return nums[$blank$]
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]`, `2` → `[4, 5]`
  - `[1, 2, 3]`, `5` → `[1, 2, 3]`
  - `[10]`, `1` → `[10]`

---

### 문제 3 (빈칸) – 리스트 역순 (인덱싱)

- **문제 설명**  
  정수 리스트 `nums`를 역순으로 뒤집은 새 리스트를 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 역순 리스트

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    result = []
    for i in range(len(nums) - 1, $blank$, -1):
        result.append(nums[i])
    return result
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4]` → `[4, 3, 2, 1]`
  - `[1]` → `[1]`
  - `[]` → `[]`

---

### 문제 4 (빈칸) – 짝수 개수 (조건식)

- **문제 설명**  
  정수 리스트 `nums`에서 짝수의 개수를 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 짝수 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    count = 0
    for x in nums:
        if x $blank$ 2 $blank$ 0:
            count += 1
    return count
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]` → `2`
  - `[2, 4, 6]` → `3`
  - `[1, 3, 5]` → `0`

---

### 문제 5 (빈칸) – 10 이상인 첫 인덱스

- **문제 설명**  
  정수 리스트 `nums`에서 값이 10 이상인 **가장 처음 등장하는 인덱스**를 반환하는 `solution` 함수를 완성하세요. 없으면 -1을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 인덱스(정수) 또는 -1

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    for i in range($blank$):
        if nums[i] $blank$ 10:
            return $blank$
    return -1
```

- **예시 테스트케이스**
  - `[3, 7, 10, 15]` → `2`
  - `[1, 2, 3]` → `-1`
  - `[10]` → `0`

---

### 문제 6 (빈칸) – 클래스: 점수 관리

- **문제 설명**  
  점수 리스트를 관리하는 `ScoreManager` 클래스를 완성하세요.  
  - 생성자에서 점수 리스트를 받아 저장  
  - `average()`: 저장된 점수의 평균을 반환 (소수 첫째 자리)  
  - `pass_count(threshold)`: threshold 이상인 점수의 개수 반환  

- **코드 (빈칸 채우기)**

```python
class ScoreManager:
    def $blank$(self, scores):
        self.scores = $blank$

    def average(self):
        if not self.scores:
            return 0.0
        return round($blank$(self.scores) / len(self.scores), 1)

    def pass_count(self, threshold):
        cnt = 0
        for s in self.scores:
            if s $blank$ threshold:
                cnt += 1
        return cnt


def solution(scores, threshold):
    m = ScoreManager($blank$)
    return m.average(), m.pass_count(threshold)
```

- **예시 테스트케이스**
  - `scores = [70, 80, 90]`, `threshold = 75` → `(80.0, 2)`
  - `scores = [50, 60]`, `threshold = 60` → `(55.0, 1)`

---

### 문제 7 (빈칸) – 클래스 상속: 확장 카운터

- **문제 설명**  
  `Counter` 클래스는 `value`를 1씩 증가시키는 `inc()`를 가집니다.  
  `DoubleCounter`는 `Counter`를 상속받아, `inc()` 호출 시 `value`가 2씩 증가하도록 합니다.  
  생성자에서 초기값을 받아 설정합니다.

- **코드 (빈칸 채우기)**

```python
class Counter:
    def __init__(self, value=0):
        self.value = value

    def inc(self):
        self.value += 1


class DoubleCounter($blank$):
    def __init__(self, value=0):
        $blank$($blank$, value)

    def inc(self):
        self.value += $blank$


def solution(init_val):
    c = DoubleCounter(init_val)
    c.inc()
    c.inc()
    return c.value
```

- **예시 테스트케이스**
  - `init_val = 0` → `4`
  - `init_val = 5` → `9`
  - `init_val = 10` → `14`

---

### 문제 8 (빈칸) – 클래스: 스택

- **문제 설명**  
  정수를 저장하는 간단한 `Stack` 클래스를 완성하세요.  
  - `push(x)`: x를 스택에 추가  
  - `pop()`: 맨 위 원소 제거 후 반환 (비어 있으면 None)  
  - `size()`: 원소 개수 반환  

- **코드 (빈칸 채우기)**

```python
class Stack:
    def __init__(self):
        self.items = $blank$

    def push(self, x):
        self.items.$blank$(x)

    def pop(self):
        if $blank$:
            return None
        return self.items.$blank$()

    def size(self):
        return $blank$(self.items)


def solution(ops):
    s = Stack()
    for op in ops:
        if op[0] == 'push':
            s.push(op[1])
        else:
            s.pop()
    return s.size(), s.pop()
```

- **예시 테스트케이스**
  - `ops = [('push', 1), ('push', 2), ('pop', None), ('push', 3)]` → `(2, 3)`  
    (마지막에 size=2, pop하면 3)

---

### 문제 9 (빈칸) – 클래스: 사각형 넓이

- **문제 설명**  
  `Rectangle` 클래스는 `width`, `height`를 받아 저장하고,  
  `area()` 메서드로 넓이를 반환합니다.  
  `Square` 클래스는 `Rectangle`을 상속받아, 한 변의 길이만 받아 정사각형으로 처리합니다.

- **코드 (빈칸 채우기)**

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = $blank$

    def area(self):
        return self.width $blank$ self.height


class Square($blank$):
    def __init__(self, side):
        super().__init__($blank$, side)


def solution(side):
    sq = Square(side)
    return sq.area()
```

- **예시 테스트케이스**
  - `side = 5` → `25`
  - `side = 10` → `100`

---

### 문제 10 (빈칸) – 클래스: 문자열 래퍼

- **문제 설명**  
  `TextWrapper` 클래스는 문자열을 저장하고,  
  - `reverse()`: 문자열을 뒤집은 값 반환  
  - `word_count()`: 공백으로 나눈 단어 개수 반환  
  - `replace_char(old, new)`: `old` 문자를 `new`로 바꾼 새 문자열 반환  

- **코드 (빈칸 채우기)**

```python
class TextWrapper:
    def __init__(self, text):
        self.text = $blank$

    def reverse(self):
        return self.text[$blank$]

    def word_count(self):
        return len(self.text.$blank$())

    def replace_char(self, old, new):
        return self.text.$blank$(old, new)


def solution(text, old_ch, new_ch):
    w = TextWrapper(text)
    return w.reverse(), w.word_count(), w.replace_char($blank$)
```

- **예시 테스트케이스**
  - `text = "hello world"`, `old_ch = "o"`, `new_ch = "x"`  
    → `("dlrow olleh", 2, "hellx wxrld")`
  - `text = "a b c"`, `old_ch = " "`, `new_ch = "-"`  
    → `("c b a", 3, "a-b-c")`

---

위 10문제는 클래스(생성자, 메서드, 상속)와 인덱싱·조건식 등 자주 실수하는 부분을 빈칸으로 두었습니다.  
각 문제의 빈칸을 채워 예시와 같은 결과가 나오도록 완성해 보세요.
