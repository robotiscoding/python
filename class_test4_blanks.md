총 10문제이며, **모두 빈칸 채우기**입니다.  
각 문제의 빈칸(`$blank$`)을 올바른 코드로 채워 예시와 같은 결과가 나오도록 완성하세요.

---

### 문제 1 – 홀수만의 합

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  리스트에 있는 **홀수인 원소들만** 모두 더한 값을 반환하는 `solution` 함수를 완성하세요.  
  홀수가 하나도 없으면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 홀수들의 합(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    total = 0
    for x in nums:
        if x $blank$ 2 != 0:
            total $blank$ x
    return total
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]` → `9`
  - `[2, 4, 6]` → `0`
  - `[1, 1, 1]` → `3`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3, 4, 5]))
print(solution([2, 4, 6]))
print(solution([1, 1, 1]))
```

---

### 문제 2 – 가장 긴 연속 동일 문자 길이

- **문제 설명**  
  문자열 `s`가 주어집니다.  
  **같은 문자가 연속해서** 나오는 구간 중, 가장 긴 구간의 길이를 반환하는 `solution` 함수를 완성하세요.  
  빈 문자열이면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `s` (문자열)
  - 반환값: 최대 연속 길이(정수)

- **코드 (빈칸 채우기)**

```python
def solution(s):
    if not s:
        return 0
    best = 1
    cnt = 1
    for i in range(1, $blank$(s)):
        if s[i] == s[i - 1]:
            cnt += 1
        else:
            if cnt > best:
                best = cnt
            cnt = $blank$
    if cnt > best:
        best = cnt
    return best
```

- **예시 테스트케이스**
  - `"aaabbbcccc"` → `4`
  - `"abc"` → `1`
  - `"aaa"` → `3`

- **테스트 실행 코드**
```python
print(solution("aaabbbcccc"))
print(solution("abc"))
print(solution("aaa"))
```

---

### 문제 3 – 리스트 오른쪽 회전

- **문제 설명**  
  정수 리스트 `nums`와 양의 정수 `k`가 주어집니다.  
  리스트를 **오른쪽으로 k칸** 회전한 결과를 반환하는 `solution` 함수를 완성하세요.  
  `k`가 리스트 길이보다 클 수 있으며, 그 경우에도 올바르게 회전해야 합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `k` (양의 정수)
  - 반환값: 회전된 리스트

- **코드 (빈칸 채우기)**

```python
def solution(nums, k):
    if not nums:
        return []
    n = len(nums)
    k = k $blank$ n
    return nums[n - k:] + nums[:n - k]
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]`, `2` → `[4, 5, 1, 2, 3]`
  - `[1, 2]`, `3` → `[2, 1]`
  - `[7]`, `5` → `[7]`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3, 4, 5], 2))
print(solution([1, 2], 3))
print(solution([7], 5))
```

---

### 문제 4 – 부분 문자열 포함 여부

- **문제 설명**  
  문자열 `s`와 `sub`가 주어집니다.  
  `s` 안에 `sub`가 **연속으로** 등장하면 `True`, 아니면 `False`를 반환하는 `solution` 함수를 완성하세요.  
  `sub`가 빈 문자열이면 항상 `True`를 반환합니다.

- **함수 설명**
  - 매개변수: `s` (문자열), `sub` (문자열)
  - 반환값: 포함 여부 (True / False)

- **코드 (빈칸 채우기)**

```python
def solution(s, sub):
    if not sub:
        return True
    for i in range(len(s) - len(sub) + 1):
        if s[i:i + len(sub)] $blank$ sub:
            return True
    return $blank$
```

- **예시 테스트케이스**
  - `"hello"`, `"ell"` → `True`
  - `"hello"`, `"ol"` → `False`
  - `"abc"`, `""` → `True`

- **테스트 실행 코드**
```python
print(solution("hello", "ell"))
print(solution("hello", "ol"))
print(solution("abc", ""))
```

---

### 문제 5 – 두 수의 최대공약수

- **문제 설명**  
  양의 정수 `a`와 `b`가 주어집니다.  
  **유클리드 호제법**을 이용하여 두 수의 최대공약수를 반환하는 `solution` 함수를 완성하세요.  
  `a`와 `b`는 양수임이 보장됩니다.

- **함수 설명**
  - 매개변수: `a` (양의 정수), `b` (양의 정수)
  - 반환값: 최대공약수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(a, b):
    while b != 0:
        r = a $blank$ b
        a = b
        b = $blank$
    return a
```

- **예시 테스트케이스**
  - `12`, `18` → `6`
  - `7`, `13` → `1`
  - `24`, `8` → `8`

- **테스트 실행 코드**
```python
print(solution(12, 18))
print(solution(7, 13))
print(solution(24, 8))
```

---

### 문제 6 – 피크 요소 인덱스

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  인덱스 `i`에 대해 `nums[i]`가 **양쪽 이웃보다 크면** 피크입니다.  
  가장 왼쪽 피크의 인덱스를 반환하는 `solution` 함수를 완성하세요.  
  피크가 없으면 -1을 반환합니다. 양 끝은 한쪽 이웃만 비교합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 피크 인덱스(정수) 또는 -1

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    if len(nums) < 2:
        return -1
    for i in range(1, len(nums) - 1):
        if nums[i] > nums[i - 1] and nums[i] $blank$ nums[i + 1]:
            return i
    if nums[0] > nums[1]:
        return $blank$
    if nums[-1] > nums[-2]:
        return len(nums) - 1
    return -1
```

- **예시 테스트케이스**
  - `[1, 3, 2, 5, 4]` → `1`
  - `[5, 4, 3, 2, 1]` → `0`
  - `[1, 2, 3, 4, 5]` → `4`

- **테스트 실행 코드**
```python
print(solution([1, 3, 2, 5, 4]))
print(solution([5, 4, 3, 2, 1]))
print(solution([1, 2, 3, 4, 5]))
```

---

### 문제 7 – 연속 부분배열 최대 합

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  **연속한 원소들**로 이루어진 부분 배열 중, 합이 가장 큰 값을 반환하는 `solution` 함수를 완성하세요.  
  리스트가 비어 있으면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 최대 연속 부분합(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    if not nums:
        return 0
    best = nums[0]
    cur = 0
    for x in nums:
        cur = cur + x
        if cur > best:
            best = cur
        if cur $blank$ 0:
            cur = 0
    return best
```

- **예시 테스트케이스**
  - `[-2, 1, -3, 4, -1, 2, 1, -5, 4]` → `6`
  - `[1, 2, 3]` → `6`
  - `[-1, -2, -3]` → `-1`

- **테스트 실행 코드**
```python
print(solution([-2, 1, -3, 4, -1, 2, 1, -5, 4]))
print(solution([1, 2, 3]))
print(solution([-1, -2, -3]))
```

---

### 문제 8 – 오름차순 정렬된 두 리스트 병합

- **문제 설명**  
  오름차순으로 정렬된 정수 리스트 `a`와 `b`가 주어집니다.  
  두 리스트를 **합쳐서** 오름차순으로 정렬한 하나의 리스트를 반환하는 `solution` 함수를 완성하세요.  
  반드시 두 리스트를 **순차적으로 비교**하며 병합하는 방식을 사용해야 합니다.

- **함수 설명**
  - 매개변수: `a` (오름차순 리스트), `b` (오름차순 리스트)
  - 반환값: 병합된 오름차순 리스트

- **코드 (빈칸 채우기)**

```python
def solution(a, b):
    result = []
    i = 0
    j = 0
    while i < len(a) and j < len(b):
        if a[i] <= b[j]:
            result.append(a[i])
            i += 1
        else:
            result.$blank$(b[j])
            j += 1
    result = result + a[i:] + b[$blank$:]
    return result
```

- **예시 테스트케이스**
  - `[1, 3, 5]`, `[2, 4, 6]` → `[1, 2, 3, 4, 5, 6]`
  - `[1, 2]`, `[3, 4, 5]` → `[1, 2, 3, 4, 5]`
  - `[]`, `[1]` → `[1]`

- **테스트 실행 코드**
```python
print(solution([1, 3, 5], [2, 4, 6]))
print(solution([1, 2], [3, 4, 5]))
print(solution([], [1]))
```

---

### 문제 9 – 괄호 깊이의 최댓값

- **문제 설명**  
  문자열 `s`는 `(`와 `)`만 포함합니다.  
  괄호가 열릴 때마다 깊이가 1씩 증가하고, 닫힐 때마다 1씩 감소합니다.  
  문자열을 처음부터 읽으며 **깊이가 가장 컸던 값**을 반환하는 `solution` 함수를 완성하세요.  
  괄호 짝이 맞지 않으면 -1을 반환합니다.

- **함수 설명**
  - 매개변수: `s` (괄호 문자열)
  - 반환값: 최대 깊이(정수) 또는 -1

- **코드 (빈칸 채우기)**

```python
def solution(s):
    depth = 0
    best = 0
    for ch in s:
        if ch == '(':
            depth += 1
            if depth > best:
                best = $blank$
        elif ch == ')':
            depth -= 1
            if depth < 0:
                return -1
    if depth $blank$ 0:
        return -1
    return best
```

- **예시 테스트케이스**
  - `"((()))"` → `3`
  - `"()(())"` → `2`
  - `"())"` → `-1`

- **테스트 실행 코드**
```python
print(solution("((()))"))
print(solution("()(())"))
print(solution("())"))
```

---

### 문제 10 – 소수 개수 세기

- **문제 설명**  
  양의 정수 `n`이 주어집니다.  
  `2` 이상 `n` 이하의 정수 중 **소수**의 개수를 반환하는 `solution` 함수를 완성하세요.  
  `n`은 2 이상입니다.  
  소수는 1과 자기 자신으로만 나누어떨어지는 수입니다.

- **함수 설명**
  - 매개변수: `n` (양의 정수, 2 이상)
  - 반환값: 소수 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(n):
    count = 0
    for num in range(2, n + 1):
        prime = True
        for i in range(2, int(num ** 0.5) + 1):
            if num $blank$ i == 0:
                prime = False
                break
        if prime:
            count += 1
    return $blank$
```

- **예시 테스트케이스**
  - `10` → `4` (2, 3, 5, 7)
  - `2` → `1`
  - `20` → `8`

- **테스트 실행 코드**
```python
print(solution(10))
print(solution(2))
print(solution(20))
```

---

위 10문제는 리스트, 문자열, 반복문, 조건문 등 파이썬 기본 문법을 활용합니다.  
빈칸을 채워 예시와 같은 결과가 나오도록 완성해 보세요.
