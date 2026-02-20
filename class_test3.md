총 10문제이며, **1~5번은 빈칸 채우기**, **6~10번은 디버깅 문제**입니다.  

---

### 문제 1 (빈칸) – 합이 target인 연속 부분 배열 개수

- **문제 설명**  
  정수 리스트 `nums`와 정수 `target`이 주어집니다.  
  **연속한 원소들의 합**이 `target`이 되는 경우의 수를 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `target` (정수)
  - 반환값: 조건을 만족하는 연속 부분 배열의 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums, target):
    count = 0
    for i in range(len(nums)):
        s = 0
        for j in range(i, $blank$):
            s += nums[j]
            if s $blank$ target:
                count += 1
    return count
```

- **예시 테스트케이스**
  - `[1, 2, 3]`, `3` → `2`
  - `[1, -1, 1, -1]`, `0` → `4`
  - `[1, 1, 1]`, `2` → `2`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3], 3))
print(solution([1, -1, 1, -1], 0))
print(solution([1, 1, 1], 2))
```

---

### 문제 2 (빈칸) – 여러 괄호 종류 유효성 검사

- **문제 설명**  
  문자열 `s`는 `(`, `)`, `[`, `]`, `{`, `}`만 포함합니다.  
  괄호 짝과 순서가 올바르면 `True`, 아니면 `False`를 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 유효한 괄호열 여부 (True / False)

- **코드 (빈칸 채우기)**

```python
def solution(s):
    stack = []
    pair = {')': '(', ']': '[', '}': $blank$}
    for ch in s:
        if ch in '([{':
            stack.$blank$(ch)
        elif ch in ')]}':
            if not stack or stack[-1] != pair[ch]:
                return False
            stack.$blank$()
    return len(stack) == $blank$
```

- **예시 테스트케이스**
  - `"([])"` → `True`
  - `"([)]"` → `False`
  - `"((()))[]"` → `True`
  - `"["` → `False`

- **테스트 실행 코드**
```python
print(solution("([])"))
print(solution("([)]"))
print(solution("((()))[]"))
print(solution("["))
```

---

### 문제 3 (빈칸) – 중복 제거 후 k번째로 작은 수

- **문제 설명**  
  정수 리스트 `nums`에서 **중복을 제거**한 뒤 오름차순 정렬했을 때,  
  **k번째로 작은 수**를 반환하는 `solution` 함수를 완성하세요.  
  `k`가 1보다 작거나, 서로 다른 수의 개수보다 크면 `None`을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `k` (양의 정수)
  - 반환값: k번째로 작은 수(정수) 또는 None

- **코드 (빈칸 채우기)**

```python
def solution(nums, k):
    uniq = sorted($blank$(nums))
    if k < 1 or k > $blank$:
        return None
    return uniq[$blank$]
```

- **예시 테스트케이스**
  - `[3, 1, 2, 2, 4]`, `2` → `2`
  - `[10, 10, 10]`, `1` → `10`
  - `[1, 2, 3]`, `5` → `None`

- **테스트 실행 코드**
```python
print(solution([3, 1, 2, 2, 4], 2))
print(solution([10, 10, 10], 1))
print(solution([1, 2, 3], 5))
```

---

### 문제 4 (빈칸) – 구간 병합 후 개수

- **문제 설명**  
  `[start, end]` 형태의 구간들이 담긴 리스트 `intervals`가 주어집니다.  
  겹치는 구간을 **병합**한 뒤, 남은 구간의 개수를 반환하는 `solution` 함수를 완성하세요.  
  빈 리스트면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `intervals` (구간 리스트)
  - 반환값: 병합 후 구간 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(intervals):
    if not intervals:
        return 0
    arr = sorted(intervals, key=lambda x: x[$blank$])
    merged = [arr[0]]
    for i in range(1, len(arr)):
        last = merged[-1]
        if arr[i][0] $blank$ last[1]:
            merged[-1] = [last[0], max(last[1], arr[i][1])]
        else:
            merged.$blank$(arr[i])
    return len(merged)
```

- **예시 테스트케이스**
  - `[[1, 3], [2, 6], [8, 10]]` → `2`
  - `[[1, 4], [4, 5]]` → `1`
  - `[[1, 2], [3, 4]]` → `2`

- **테스트 실행 코드**
```python
print(solution([[1, 3], [2, 6], [8, 10]]))
print(solution([[1, 4], [4, 5]]))
print(solution([[1, 2], [3, 4]]))
```

---

### 문제 5 (빈칸) – 두 번째로 많이 등장한 값

- **문제 설명**  
  정수 리스트 `nums`에서 **두 번째로 많이 등장한 값**을 반환하는 `solution` 함수를 완성하세요.  
  동률이면 더 작은 값을 선택하고, 서로 다른 값이 2개 미만이면 `None`을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 두 번째 최빈값(정수) 또는 None

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    freq = {}
    for x in nums:
        freq[x] = freq.get(x, 0) + $blank$
    if len(freq) < 2:
        return None
    counts = sorted(set(freq.$blank$()), reverse=True)
    second = counts[1]
    cands = [k for k, v in freq.items() if v == second]
    return $blank$(cands)
```

- **예시 테스트케이스**
  - `[1, 2, 2, 3, 3, 3]` → `2`
  - `[1, 1, 2, 2]` → `2`
  - `[7, 7, 7]` → `None`

- **테스트 실행 코드**
```python
print(solution([1, 2, 2, 3, 3, 3]))
print(solution([1, 1, 2, 2]))
print(solution([7, 7, 7]))
```

---

### 문제 6 (디버깅) – 정렬된 리스트에 삽입 위치

- **문제 설명**  
  오름차순 정렬된 정수 리스트 `nums`와 값 `target`이 주어질 때,  
  `target`을 넣어도 오름차순이 유지되는 **가장 왼쪽 인덱스**를 반환하는 `solution` 함수입니다.  
  아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `nums` (오름차순 리스트), `target` (정수)
  - 반환값: 삽입 인덱스(정수)

- **코드 (디버깅)**

```python
def solution(nums, target):
    lo, hi = 0, len(nums) - 1
    while lo < hi:
        mid = (lo + hi) // 2
        if nums[mid] < target:
            lo = mid
        else:
            hi = mid
    return lo if nums and nums[lo] >= target else len(nums)
```

- **예시 테스트케이스**
  - `[1, 3, 5, 7]`, `4` → `2`
  - `[1, 2, 2, 2, 3]`, `2` → `1`
  - `[1, 2, 3]`, `5` → `3`

- **테스트 실행 코드**
```python
print(solution([1, 3, 5, 7], 4))
print(solution([1, 2, 2, 2, 3], 2))
print(solution([1, 2, 3], 5))
```

---

### 문제 7 (디버깅) – 중복 없는 최장 부분 문자열 길이

- **문제 설명**  
  문자열 `s`에서 **같은 문자가 두 번 이상 나오지 않는** 가장 긴 연속 부분 문자열의 길이를 구하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 최대 길이(정수)

- **코드 (디버깅)**

```python
def solution(s):
    seen = {}
    start = 0
    best = 0
    for i, ch in enumerate(s):
        if ch in seen and seen[ch] >= start:
            start = seen[ch] + 1
        seen[ch] = i
        length = i - start
        if length > best:
            best = length
    return best
```

- **예시 테스트케이스**
  - `"abcabcbb"` → `3`
  - `"bbbbb"` → `1`
  - `"pwwkew"` → `3`

- **테스트 실행 코드**
```python
print(solution("abcabcbb"))
print(solution("bbbbb"))
print(solution("pwwkew"))
```

---

### 문제 8 (디버깅) – 합이 target인 두 수 인덱스 쌍 개수

- **문제 설명**  
  정수 리스트 `numbers`와 정수 `target`이 주어질 때,  
  `i < j` 이면서 `numbers[i] + numbers[j] == target` 인 쌍 `(i, j)`의 개수를 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `numbers` (정수 리스트), `target` (정수)
  - 반환값: 조건을 만족하는 쌍의 개수(정수)

- **코드 (디버깅)**

```python
def solution(numbers, target):
    count = 0
    for i in range(len(numbers)):
        for j in range(len(numbers)):
            if i < j and numbers[i] + numbers[j] == target:
                count += 1
    return count
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]`, `5` → `2`
  - `[0, 0, 0]`, `0` → `3`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3, 4, 5], 5))
print(solution([0, 0, 0], 0))
```

---

### 문제 9 (디버깅) – 팩토리얼

- **문제 설명**  
  양의 정수 `n`에 대해 `n!`(1 × 2 × … × n)을 반환하는 `solution` 함수입니다.  
  아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `n` (양의 정수)
  - 반환값: `n!`(정수)

- **코드 (디버깅)**

```python
def solution(n):
    result = 1
    for i in range(1, n):
        result *= i
    return result
```

- **예시 테스트케이스**
  - `5` → `120`
  - `3` → `6`
  - `1` → `1`

- **테스트 실행 코드**
```python
print(solution(5))
print(solution(3))
print(solution(1))
```

---

### 문제 10 (디버깅) – 연속 중복 문자 제거

- **문제 설명**  
  문자열 `s`에서 **연속하여 같은 문자**가 나오면 하나로 줄인 문자열을 반환하는 `solution` 함수입니다.  
  아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 중복이 제거된 문자열

- **코드 (디버깅)**

```python
def solution(s):
    if not s:
        return ''
    result = s[0]
    for ch in s[1:]:
        if ch == result[-1]:
            result += ch
    return result
```

- **예시 테스트케이스**
  - `"aaabbcaa"` → `"abca"`
  - `"abc"` → `"abc"`
  - `""` → `""`

- **테스트 실행 코드**
```python
print(solution("aaabbcaa"))
print(solution("abc"))
print(solution(""))
```

---
