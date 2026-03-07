총 10문제이며, **모두 빈칸 채우기**입니다.  
각 문제의 빈칸(`$blank$`)을 올바른 코드로 채워 예시와 같은 결과가 나오도록 완성하세요.  


---

### 문제 1 – 연속 부분배열 최대 곱

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다. (음수 포함)  
  **연속한 원소들**의 곱이 최대가 되는 값을 반환하세요.  
  음수×음수=양수이므로, 최솟값도 함께 추적해야 합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 최대 연속 곱(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    if not nums:
        return 0
    cur_max = cur_min = best = nums[0]
    for i in range(1, len(nums)):
        x = nums[i]
        temp = cur_max
        cur_max = max(x, cur_max * x, cur_min $blank$ x)
        cur_min = min(x, temp * x, cur_min * x)
        best = max(best, $blank$)
    return best
```

- **예시 테스트케이스**
  - `[2, 3, -2, 4]` → `6`
  - `[-2, 0, -1]` → `0`
  - `[2, -1, 3, -2]` → `12`

- **테스트 실행 코드**

```python
print(solution([2, 3, -2, 4]))
print(solution([-2, 0, -1]))
print(solution([2, -1, 3, -2]))
```

---

### 문제 2 – 모노톤 스택: 다음으로 큰 요소의 인덱스

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  각 위치 `i`에 대해, `i`보다 **오른쪽**에 있으면서 `nums[i]`보다 **처음으로 큰 값**의 인덱스를 반환하는 리스트를 만드세요.  
  그러한 인덱스가 없으면 해당 위치에는 `-1`을 넣습니다.  
  **스택**을 사용해 O(n)에 풀어야 합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 각 위치의 "다음으로 큰 요소" 인덱스 리스트

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    n = len(nums)
    result = [-1] * n
    stack = []
    for i in range(n):
        while stack and nums[i] > nums[stack[$blank$]]:
            idx = stack.pop()
            result[idx] = $blank$
        stack.append(i)
    return result
```

- **예시 테스트케이스**
  - `[2, 1, 3, 4]` → `[2, 2, 3, -1]`
  - `[5, 4, 3, 2]` → `[-1, -1, -1, -1]`
  - `[1, 3, 2, 4]` → `[1, 3, 3, -1]`

- **테스트 실행 코드**

```python
print(solution([2, 1, 3, 4]))
print(solution([5, 4, 3, 2]))
print(solution([1, 3, 2, 4]))
```

---

### 문제 3 – LCS (최장 공통 부분 수열) 길이

- **문제 설명**  
  두 문자열 `a`, `b`가 주어집니다.  
  **최장 공통 부분 수열(Longest Common Subsequence)**의 길이를 반환하세요.  
  부분 수열은 원래 순서를 유지하면서 일부 문자만 뽑은 것입니다.  
  2차원 DP를 사용하세요.

- **함수 설명**
  - 매개변수: `a` (문자열), `b` (문자열)
  - 반환값: LCS 길이(정수)

- **코드 (빈칸 채우기)**

```python
def solution(a, b):
    m, n = len(a), len(b)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if a[i - 1] == b[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] $blank$ 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j $blank$ 1])
    return dp[m][n]
```

- **예시 테스트케이스**
  - `"abcde"`, `"ace"` → `3`
  - `"abc"`, `"def"` → `0`
  - `"abc"`, `"abc"` → `3`

- **테스트 실행 코드**

```python
print(solution("abcde", "ace"))
print(solution("abc", "def"))
print(solution("abc", "abc"))
```

---

### 문제 4 – 에라토스테네스의 체 (n 이하 소수 개수)

- **문제 설명**  
  양의 정수 `n`이 주어집니다.  
  `2` 이상 `n` 이하의 **소수 개수**를 반환하세요.  
  에라토스테네스의 체를 사용하고, `i`의 배수를 지울 때 `i*i`부터 시작해 `i`씩 증가시키세요.

- **함수 설명**
  - 매개변수: `n` (양의 정수)
  - 반환값: 소수 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(n):
    if n < 2:
        return 0
    is_prime = [True] * (n + 1)
    is_prime[0] = is_prime[1] = False
    i = 2
    while i * i <= n:
        if is_prime[i]:
            for j in range(i * i, n + 1, $blank$):
                is_prime[j] = False
        i += 1
    return sum(is_prime)
```

- **예시 테스트케이스**
  - `10` → `4`
  - `2` → `1`
  - `20` → `8`

- **테스트 실행 코드**

```python
print(solution(10))
print(solution(2))
print(solution(20))
```

---

### 문제 5 – 행렬 90도 시계 방향 회전

- **문제 설명**  
  정사각 2차원 리스트 `matrix`가 주어집니다.  
  행렬을 **90도 시계 방향**으로 회전시킨 결과를 **제자리(in-place)**로 반환하세요.  
  `matrix[i][j]` → `matrix[j][n-1-i]` (n은 한 변 길이)

- **함수 설명**
  - 매개변수: `matrix` (정사각 2차원 리스트)
  - 반환값: 회전된 행렬 (같은 matrix 수정 후 반환)

- **코드 (빈칸 채우기)**

```python
def solution(matrix):
    n = len(matrix)
    for i in range(n // 2):
        for j in range(i, n - 1 - i):
            tmp = matrix[i][j]
            matrix[i][j] = matrix[n - 1 - j][i]
            matrix[n - 1 - j][i] = matrix[n - 1 - i][n - 1 - j]
            matrix[n - 1 - i][n - 1 - j] = matrix[j][n - 1 $blank$ i]
            matrix[j][n - 1 - i] = tmp
    return matrix
```

- **예시 테스트케이스**
  - `[[1,2],[3,4]]` → `[[3,1],[4,2]]`
  - `[[1,2,3],[4,5,6],[7,8,9]]` → `[[7,4,1],[8,5,2],[9,6,3]]`

- **테스트 실행 코드**

```python
print(solution([[1,2],[3,4]]))
print(solution([[1,2,3],[4,5,6],[7,8,9]]))
```

---

### 문제 6 – 삽입 정렬 (제자리 정렬)

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  **삽입 정렬**로 오름차순 정렬하세요.  
  `i`번째 원소를 왼쪽 정렬된 구간에 끼워 넣을 때, 뒤에서부터 비교하며 알맞은 자리를 찾습니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트, 제자리 수정)
  - 반환값: 정렬된 리스트 (같은 nums 반환)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    for i in range(1, len(nums)):
        key = nums[i]
        j = i - 1
        while j >= 0 and nums[j] $blank$ key:
            nums[j + 1] = nums[j]
            j -= 1
        nums[$blank$] = key
    return nums
```

- **예시 테스트케이스**
  - `[5, 2, 4, 6, 1]` → `[1, 2, 4, 5, 6]`
  - `[3, 1, 2]` → `[1, 2, 3]`

- **테스트 실행 코드**

```python
print(solution([5, 2, 4, 6, 1]))
print(solution([3, 1, 2]))
```

---

### 문제 7 – 부분집합 합이 target인 개수 (재귀)

- **문제 설명**  
  양의 정수 리스트 `nums`와 `target`이 주어집니다.  
  원소를 **각각 최대 한 번** 사용해 합이 `target`이 되는 **부분집합의 개수**를 반환하세요.  
  재귀로 모든 경우를 탐색합니다.

- **함수 설명**
  - 매개변수: `nums` (양의 정수 리스트), `target` (양의 정수)
  - 반환값: 부분집합 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums, target):
    def go(idx, rest):
        if rest == 0:
            return 1
        if rest < 0 or idx $blank$ len(nums):
            return 0
        return go(idx + 1, rest) + go(idx + 1, rest $blank$ nums[idx])
    return go(0, target)
```

- **예시 테스트케이스**
  - `[1, 2, 3]`, `4` → `1`  (1+3)
  - `[1, 2, 3, 4]`, `5` → `2`  (1+4, 2+3)
  - `[1]`, `1` → `1`

- **테스트 실행 코드**

```python
print(solution([1, 2, 3], 4))
print(solution([1, 2, 3, 4], 5))
print(solution([1], 1))
```

---

### 문제 8 – 괄호를 최소로 추가해 유효하게

- **문제 설명**  
  문자열 `s`는 `(` 와 `)` 만 포함합니다.  
  괄호를 **최소 개수**로 추가해서 짝이 맞는 올바른 괄호열로 만들 때, 추가해야 하는 **괄호 개수**를 반환하세요.  
  스택을 사용하지 않고, 필요한 `(` 개수와 `)` 개수만 추적합니다.

- **함수 설명**
  - 매개변수: `s` (괄호 문자열)
  - 반환값: 추가해야 할 괄호의 최소 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(s):
    need_left = 0
    need_right = 0
    for ch in s:
        if ch == '(':
            need_right += 1
        else:
            need_right -= 1
            if need_right < 0:
                need_left += 1
                need_right = $blank$
    return need_left + need_right
```

- **예시 테스트케이스**
  - `"(()"` → `1`  (오른쪽에 ) 하나 추가)
  - `"())"` → `1`  (왼쪽에 ( 하나 추가)
  - `"()))(("` → `4`

- **테스트 실행 코드**

```python
print(solution("(()"))
print(solution("())"))
print(solution("()))(("))
```

---

### 문제 9 – 두 포인터: 정렬된 배열에서 두 수의 합

- **문제 설명**  
  오름차순 정렬된 정수 리스트 `nums`와 `target`이 주어집니다.  
  합이 `target`이 되는 **두 수의 인덱스**를 찾아 `(i, j)` 튜플로 반환하세요.  
  반드시 `i < j`이고, 답이 유일하다고 가정합니다.  
  두 포인터를 양끝에서 시작해 O(n)에 풀어야 합니다.

- **함수 설명**
  - 매개변수: `nums` (오름차순 리스트), `target` (정수)
  - 반환값: `(i, j)` 튜플 (인덱스)

- **코드 (빈칸 채우기)**

```python
def solution(nums, target):
    left = 0
    right = len(nums) - 1
    while left < right:
        s = nums[left] + nums[right]
        if s == target:
            return (left, right)
        if s < target:
            left += 1
        else:
            right $blank$ 1
    return (-1, -1)
```

- **예시 테스트케이스**
  - `[2, 7, 11, 15]`, `9` → `(0, 1)`
  - `[1, 2, 3, 4]`, `6` → `(1, 2)`

- **테스트 실행 코드**

```python
print(solution([2, 7, 11, 15], 9))
print(solution([1, 2, 3, 4], 6))
```

---

### 문제 10 – 다음 순열 (Next Permutation, 제자리)

- **문제 설명**  
  정수 리스트 `nums`가 주어집니다.  
  **사전순으로 다음 순열**로 제자리 수정하고, `nums`를 반환하세요.  
  이미 마지막 순열이면 오름차순으로 바꾼 뒤 반환합니다.  
  1) 뒤에서부터 `nums[i] < nums[i+1]`인 `i` 찾기  2) `i` 뒤에서 `nums[i]`보다 큰 최소값과 교환  3) `i+1` ~ 끝을 뒤집기

- **함수 설명**
  - 매개변수: `nums` (정수 리스트, 제자리 수정)
  - 반환값: 다음 순열 리스트

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    n = len(nums)
    i = n - 2
    while i >= 0 and nums[i] >= nums[i + 1]:
        i -= 1
    if i >= 0:
        j = n - 1
        while nums[j] <= nums[i]:
            j -= 1
        nums[i], nums[j] = nums[j], nums[i]
    left, right = i + 1, n - 1
    while left $blank$ right:
        nums[left], nums[right] = nums[right], nums[left]
        left += 1
        right -= 1
    return nums
```

- **예시 테스트케이스**
  - `[1, 2, 3]` → `[1, 3, 2]`
  - `[3, 2, 1]` → `[1, 2, 3]`
  - `[1, 1, 5]` → `[1, 5, 1]`

- **테스트 실행 코드**

```python
print(solution([1, 2, 3]))
print(solution([3, 2, 1]))
print(solution([1, 1, 5]))
```

---

위 10문제는 연속 최대곱, 모노톤 스택, LCS, 에라토스테네스 체, 행렬 회전, 삽입 정렬, 부분집합 합, 괄호 추가, 두 포인터, 다음 순열 등 **어려운 알고리즘**으로 구성했습니다.  
빈칸을 채워 예시와 같은 결과가 나오도록 완성해 보세요.
</think>
검토 중: 문제 1 테스트케이스 확인 후 전체 교체를 진행합니다.
<｜tool▁calls▁begin｜><｜tool▁call▁begin｜>
StrReplace