총 10문제이며, **모두 빈칸 채우기**입니다.  
각 문제의 빈칸(`$blank$`)을 올바른 코드로 채워 예시와 같은 결과가 나오도록 완성하세요.  

---

### 문제 1 – 이진 검색 (Binary Search)

- **문제 설명**  
  오름차순으로 정렬된 정수 리스트 `nums`와 찾을 값 `target`이 주어집니다.  
  **이진 검색**을 이용해 `target`의 인덱스를 찾아 반환하세요.  
  없으면 -1을 반환합니다. 반드시 while문과 절반 나누기 방식으로 구현하세요.

- **함수 설명**
  - 매개변수: `nums` (오름차순 정렬된 리스트), `target` (정수)
  - 반환값: 인덱스(정수) 또는 -1

- **코드 (빈칸 채우기)**

```python
def solution(nums, target):
    left = 0
    right = len(nums) - 1
    while left <= right:
        mid = (left + right) $blank$ 2
        if nums[mid] == target:
            return mid
        if nums[mid] < target:
            left = mid $blank$ 1
        else:
            right = mid - 1
    return -1
```

- **예시 테스트케이스**
  - `[1, 3, 5, 7, 9]`, `5` → `2`
  - `[1, 2, 3]`, `4` → `-1`
  - `[10]`, `10` → `0`

- **테스트 실행 코드**

```python
print(solution([1, 3, 5, 7, 9], 5))
print(solution([1, 2, 3], 4))
print(solution([10], 10))
```

---

### 문제 2 – 재귀 피보나치 (메모이제이션)

- **문제 설명**  
  음이 아닌 정수 `n`이 주어집니다.  
  **재귀 함수**로 피보나치 수 `F(n)`을 구하세요.  
  `F(0)=0`, `F(1)=1`, `F(n)=F(n-1)+F(n-2)`  
  이미 계산한 값은 딕셔너리 `memo`에 저장해 중복 계산을 피합니다.

- **함수 설명**
  - 매개변수: `n` (음이 아닌 정수)
  - 반환값: `F(n)` (정수)

- **코드 (빈칸 채우기)**

```python
def solution(n):
    memo = {}
    def fib(k):
        if k <= 1:
            return k
        if k not in memo:
            memo[k] = fib(k - 1) + fib(k $blank$ 1)
        return memo[k]
    return fib($blank$)
```

- **예시 테스트케이스**
  - `7` → `13`
  - `0` → `0`
  - `10` → `55`

- **테스트 실행 코드**

```python
print(solution(7))
print(solution(0))
print(solution(10))
```

---

### 문제 3 – 두 포인터로 정렬된 리스트 합치기

- **문제 설명**  
  오름차순 정렬된 정수 리스트 `a`와 `b`가 주어집니다.  
  두 리스트를 합쳐 오름차순으로 정렬한 리스트를 반환하세요.  
  `sort()`나 `sorted()`를 사용하지 말고, **두 포인터**로 O(n)에 병합하세요.

- **함수 설명**
  - 매개변수: `a` (오름차순 리스트), `b` (오름차순 리스트)
  - 반환값: 병합된 오름차순 리스트

- **코드 (빈칸 채우기)**

```python
def solution(a, b):
    result = []
    i = 0
    j = 0
    while i < len(a) $blank$ j < len(b):
        if j >= len(b) or (i < len(a) and a[i] <= b[j]):
            result.append(a[i])
            i += 1
        else:
            result.append(b[$blank$])
            j += 1
    return result + a[i:] + b[j:]
```

- **예시 테스트케이스**
  - `[1, 4, 7]`, `[2, 5, 8]` → `[1, 2, 4, 5, 7, 8]`
  - `[]`, `[1, 2]` → `[1, 2]`
  - `[1, 1, 2]`, `[1, 3]` → `[1, 1, 1, 2, 3]`

- **테스트 실행 코드**

```python
print(solution([1, 4, 7], [2, 5, 8]))
print(solution([], [1, 2]))
print(solution([1, 1, 2], [1, 3]))
```

---

### 문제 4 – 슬라이딩 윈도우 최대 합

- **문제 설명**  
  정수 리스트 `nums`와 양의 정수 `k`가 주어집니다.  
  길이가 `k`인 **연속 부분 배열** 중 합이 가장 큰 값을 반환하세요.  
  슬라이딩 윈도우를 사용해 O(n)에 풀어야 합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `k` (양의 정수)
  - 반환값: 길이 k인 구간의 최대 합(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums, k):
    if len(nums) < k:
        return 0
    cur = sum(nums[:k])
    best = cur
    for i in range(k, len(nums)):
        cur = cur - nums[i - k] + nums[$blank$]
        if cur > best:
            best = cur
    return best
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]`, `3` → `12`
  - `[2, -1, 3, 4]`, `2` → `7`
  - `[1]`, `1` → `1`

- **테스트 실행 코드**

```python
print(solution([1, 2, 3, 4, 5], 3))
print(solution([2, -1, 3, 4], 2))
print(solution([1], 1))
```

---

### 문제 5 – 유효한 팰린드롬 (알파벳·숫자만)

- **문제 설명**  
  문자열 `s`가 주어집니다.  
  영문 알파벳과 숫자만 남기고, 대소문자를 구분하지 않았을 때 **팰린드롬**이면 True, 아니면 False를 반환하세요.  
  빈 문자열은 True입니다.

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 팰린드롬 여부 (True / False)

- **코드 (빈칸 채우기)**

```python
def solution(s):
    t = ""
    for ch in s:
        if ch.isalnum():
            t += ch.$blank$()
    left = 0
    right = len(t) - 1
    while left < right:
        if t[left] != t[right]:
            return False
        left += 1
        right $blank$ 1
    return True
```

- **예시 테스트케이스**
  - `"A man, a plan, a canal: Panama"` → `True`
  - `"race a car"` → `False`
  - `""` → `True`

- **테스트 실행 코드**

```python
print(solution("A man, a plan, a canal: Panama"))
print(solution("race a car"))
print(solution(""))
```

---

### 문제 6 – 단어 뒤집기 (공백 유지)

- **문제 설명**  
  문자열 `s`가 주어집니다.  
  **각 단어의 문자 순서만** 뒤집고, 단어 사이의 공백 개수와 위치는 그대로 유지하세요.  
  예: `"hello  world"` → `"olleh  dlrow"`

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 단어만 뒤집은 문자열

- **코드 (빈칸 채우기)**

```python
def solution(s):
    words = s.$blank$(" ")
    result = []
    for w in words:
        result.append(w[$blank$::-1])
    return " ".join(result)
```

- **예시 테스트케이스**
  - `"Let's go"` → `"s'teL og"`
  - `"a  b"` → `"a  b"`
  - `""` → `""`

- **테스트 실행 코드**

```python
print(solution("Let's go"))
print(solution("a  b"))
print(solution(""))
```

---

### 문제 7 – 리스트 중복 제거 (순서 유지, 첫 등장만)

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  **같은 값이 여러 번 나오면 처음 등장한 것만** 남기고, 원래 순서를 유지한 새 리스트를 반환하세요.  
  `set()`만 쓰면 순서가 깨지므로, seen 집합과 for문을 활용하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 중복 제거된 리스트(순서 유지)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    seen = set()
    result = []
    for x in nums:
        if x $blank$ in seen:
            seen.add(x)
            result.append(x)
    return result
```

- **예시 테스트케이스**
  - `[1, 2, 1, 3, 2, 4]` → `[1, 2, 3, 4]`
  - `[1, 1, 1]` → `[1]`
  - `[]` → `[]`

- **테스트 실행 코드**

```python
print(solution([1, 2, 1, 3, 2, 4]))
print(solution([1, 1, 1]))
print(solution([]))
```

---

### 문제 8 – 누락된 최소 양수 찾기

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  리스트에 **등장하지 않는**, 1부터 시작하는 **가장 작은 양의 정수**를 반환하세요.  
  예: `[3, 4, -1, 1]` → `2`, `[1, 2, 0]` → `3`

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 누락된 최소 양수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    seen = set(nums)
    x = 1
    while x $blank$ in seen:
        x += 1
    return x
```

- **예시 테스트케이스**
  - `[3, 4, -1, 1]` → `2`
  - `[1, 2, 0]` → `3`
  - `[7, 8, 9]` → `1`

- **테스트 실행 코드**

```python
print(solution([3, 4, -1, 1]))
print(solution([1, 2, 0]))
print(solution([7, 8, 9]))
```

---

### 문제 9 – 접두사 공통 길이 (가장 긴 공통 접두사)

- **문제 설명**  
  문자열 리스트 `strs`가 주어집니다.  
  모든 문자열에 공통으로 등장하는 **가장 긴 접두사**를 반환하세요.  
  공통 접두사가 없으면 빈 문자열을 반환합니다.  
  첫 번째 문자열을 기준으로, 한 글자씩 확인하면서 다른 문자열과 비교합니다.

- **함수 설명**
  - 매개변수: `strs` (문자열 리스트)
  - 반환값: 가장 긴 공통 접두사(문자열)

- **코드 (빈칸 채우기)**

```python
def solution(strs):
    if not strs:
        return ""
    for i in range(len(strs[0])):
        ch = strs[0][i]
        for s in strs[1:]:
            if i >= len(s) or s[i] $blank$ ch:
                return strs[0][:i]
    return strs[0]
```

- **예시 테스트케이스**
  - `["flower", "flow", "flight"]` → `"fl"`
  - `["dog", "racecar", "car"]` → `""`
  - `["ab", "ab"]` → `"ab"`

- **테스트 실행 코드**

```python
print(solution(["flower", "flow", "flight"]))
print(solution(["dog", "racecar", "car"]))
print(solution(["ab", "ab"]))
```

---

### 문제 10 – 조합의 합 (해당하는 조합 개수)

- **문제 설명**  
  양의 정수 리스트 `nums`와 목표값 `target`이 주어집니다.  
  리스트 원소를 **한 번씩만** 사용해 합이 `target`이 되는 **조합의 개수**를 반환하세요.  
  재귀(백트래킹)로 모든 경우를 탐색합니다.

- **함수 설명**
  - 매개변수: `nums` (양의 정수 리스트), `target` (양의 정수)
  - 반환값: 합이 target이 되는 조합의 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums, target):
    def go(idx, rest):
        if rest == 0:
            return 1
        if rest < 0 or idx >= len(nums):
            return 0
        return go(idx + 1, rest) + go(idx + 1, rest - nums[$blank$])
    return go(0, target)
```

- **예시 테스트케이스**
  - `[1, 2, 3]`, `4` → `1`  (1+3만 가능)
  - `[1, 2, 3, 4]`, `5` → `2`  (1+4, 2+3)
  - `[1]`, `1` → `1`

- **테스트 실행 코드**

```python
print(solution([1, 2, 3], 4))
print(solution([1, 2, 3, 4], 5))
print(solution([1], 1))
```

---
