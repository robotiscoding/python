총 10문제이며, **1~5번은 빈칸 채우기**, **6~10번은 디버깅 문제**입니다.  


---

### 문제 1 (빈칸) – 행렬 역대각선 합

- **문제 설명**  
  `n x n` 정수 행렬 `matrix`가 주어집니다.  
  오른쪽 위 → 왼쪽 아래 대각선(역대각선) 원소들의 합을 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `matrix` (n×n 정수 2차원 리스트)
  - 반환값: 역대각선 합(정수)

- **코드 (빈칸 채우기)**

```python
def solution(matrix):
    n = len(matrix)
    total = 0
    for i in range(n):
        total += matrix[i][$blank$]
    return total
```

- **예시 테스트케이스**
  - `[[1, 2], [3, 4]]` → `5`
  - `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]` → `15`
  - `[[5]]` → `5`

- **테스트 실행 코드**
```python
print(solution([[1, 2], [3, 4]]))
print(solution([[1, 2, 3], [4, 5, 6], [7, 8, 9]]))
print(solution([[5]]))
```

---

### 문제 2 (빈칸) – 행렬 전치

- **문제 설명**  
  `n x m` 행렬 `matrix`가 주어질 때, 행과 열을 바꾼 `m x n` 행렬을 반환하는 `solution` 함수를 완성하세요.

- **함수 설명**
  - 매개변수: `matrix` (2차원 정수 리스트)
  - 반환값: 전치된 2차원 리스트

- **코드 (빈칸 채우기)**

```python
def solution(matrix):
    if not matrix:
        return []
    rows = len(matrix)
    cols = len(matrix[0])
    result = []
    for j in range($blank$):
        row = []
        for i in range($blank$):
            row.append(matrix[$blank$][$blank$])
        result.append(row)
    return result
```

- **예시 테스트케이스**
  - `[[1, 2], [3, 4], [5, 6]]` → `[[1, 3, 5], [2, 4, 6]]`
  - `[[1, 2, 3]]` → `[[1], [2], [3]]`
  - `[[1], [2], [3]]` → `[[1, 2, 3]]`

- **테스트 실행 코드**
```python
print(solution([[1, 2], [3, 4], [5, 6]]))
print(solution([[1, 2, 3]]))
print(solution([[1], [2], [3]]))
```

---

### 문제 3 (빈칸) – 길이 k인 연속 구간 최대 합

- **문제 설명**  
  정수 리스트 `nums`와 양의 정수 `k`가 주어집니다.  
  길이가 정확히 `k`인 **연속 부분 수열** 중 합이 최대인 값을 반환하는 `solution` 함수를 완성하세요.  
  `k`가 리스트 길이보다 크면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트), `k` (양의 정수)
  - 반환값: 최대 합(정수) 또는 0

- **코드 (빈칸 채우기)**

```python
def solution(nums, k):
    if not nums or k > len(nums):
        return 0
    window = 0
    for i in range($blank$):
        window += nums[i]
    best = window
    for i in range(k, len(nums)):
        window = window + nums[i] $blank$ nums[$blank$]
        if window > best:
            best = window
    return best
```

- **예시 테스트케이스**
  - `[1, 2, 3, 4, 5]`, `2` → `9`
  - `[5, -1, 3, -2, 4]`, `3` → `7`
  - `[10, 20]`, `3` → `0`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3, 4, 5], 2))
print(solution([5, -1, 3, -2, 4], 3))
print(solution([10, 20], 3))
```

---

### 문제 4 (빈칸) – 행렬 테두리만 회전

- **문제 설명**  
  `n x n` 행렬 `matrix`와 정수 `k`가 주어집니다.  
  **가장 바깥 테두리**의 원소들만 시계 방향으로 `k`칸 회전한 새 행렬을 반환하는 `solution` 함수를 완성하세요.  
  안쪽 원소는 그대로 두고, 테두리만 회전합니다. `n`은 2 이상이라고 가정합니다.

- **함수 설명**
  - 매개변수: `matrix` (n×n 정수 행렬), `k` (정수, 0 이상)
  - 반환값: 테두리만 회전한 새 행렬

- **코드 (빈칸 채우기)**

```python
def solution(matrix, k):
    n = len(matrix)
    result = [row[:] for row in matrix]
    ring = []
    for j in range(n):
        ring.append(matrix[0][j])
    for i in range(1, n):
        ring.append(matrix[i][$blank$])
    for j in range(n - 2, -1, -1):
        ring.append(matrix[$blank$][j])
    for i in range(n - 2, 0, -1):
        ring.append(matrix[i][0])
    k = k % len(ring)
    ring = ring[$blank$:] + ring[:$blank$]
    idx = 0
    for j in range(n):
        result[0][j] = ring[idx]
        idx += 1
    for i in range(1, n):
        result[i][n - 1] = ring[idx]
        idx += 1
    for j in range(n - 2, -1, -1):
        result[n - 1][j] = ring[idx]
        idx += 1
    for i in range(n - 2, 0, -1):
        result[i][0] = ring[idx]
        idx += 1
    return result
```

- **예시 테스트케이스**
  - `[[1, 2], [3, 4]]`, `1` → `[[3, 1], [4, 2]]`
  - `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]`, `1` → `[[4, 1, 2], [7, 5, 3], [8, 9, 6]]`
  - `[[1, 2], [3, 4]]`, `4` → `[[1, 2], [3, 4]]`

- **테스트 실행 코드**
```python
print(solution([[1, 2], [3, 4]], 1))
print(solution([[1, 2, 3], [4, 5, 6], [7, 8, 9]], 1))
print(solution([[1, 2], [3, 4]], 4))
```

---

### 문제 5 (빈칸) – 인접한 동일 값 구간 개수

- **문제 설명**  
  정수 리스트 `nums`에서, **연속하여 같은 값**이 나오는 구간(run)의 개수를 반환하는 `solution` 함수를 완성하세요. 빈 리스트면 0을 반환합니다.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 구간 개수(정수)

- **코드 (빈칸 채우기)**

```python
def solution(nums):
    if not nums:
        return 0
    count = 1
    for i in range(1, $blank$):
        if nums[i] $blank$ nums[i - 1]:
            count += 1
    return count
```

- **예시 테스트케이스**
  - `[1, 1, 2, 2, 2, 1]` → `3`
  - `[5]` → `1`
  - `[1, 2, 3, 4]` → `4`

- **테스트 실행 코드**
```python
print(solution([1, 1, 2, 2, 2, 1]))
print(solution([5]))
print(solution([1, 2, 3, 4]))
```

---

### 문제 6 (디버깅) – 누적 합 리스트

- **문제 설명**  
  정수 리스트 `numbers`가 주어질 때, `i`번째 원소가 `numbers[0]`부터 `numbers[i]`까지의 합이 되도록 하는 누적 합 리스트를 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `numbers` (정수 리스트)
  - 반환값: 누적 합 리스트

- **코드 (디버깅)**

```python
def solution(numbers):
    result = []
    current = numbers[0]
    for n in numbers:
        current += n
        result.append(current)
    return result
```

- **예시 테스트케이스**
  - `[1, 2, 3]` → `[1, 3, 6]`
  - `[5]` → `[5]`
  - `[2, 2, 2]` → `[2, 4, 6]`

- **테스트 실행 코드**
```python
print(solution([1, 2, 3]))
print(solution([5]))
print(solution([2, 2, 2]))
```

---

### 문제 7 (디버깅) – 행렬 대각선 합

- **문제 설명**  
  `n x n` 행렬 `matrix`에서 왼쪽 위 → 오른쪽 아래 **주대각선** 원소들의 합을 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `matrix` (n×n 정수 행렬)
  - 반환값: 주대각선 합(정수)

- **코드 (디버깅)**

```python
def solution(matrix):
    total = 0
    for i in range(len(matrix)):
        total += matrix[i][len(matrix) - 1 - i]
    return total
```

- **예시 테스트케이스**
  - `[[1, 2], [3, 4]]` → `5`
  - `[[1, 2, 3], [4, 5, 6], [7, 8, 9]]` → `15`
  - `[[10]]` → `10`

- **테스트 실행 코드**
```python
print(solution([[1, 2], [3, 4]]))
print(solution([[1, 2, 3], [4, 5, 6], [7, 8, 9]]))
print(solution([[10]]))
```

---

### 문제 8 (디버깅) – 두 정렬 리스트 병합

- **문제 설명**  
  오름차순으로 정렬된 두 정수 리스트 `a`, `b`를 하나의 오름차순 리스트로 병합하여 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `a`, `b` (오름차순 정수 리스트)
  - 반환값: 병합된 오름차순 리스트

- **코드 (디버깅)**

```python
def solution(a, b):
    i = j = 0
    result = []
    while i < len(a) and j < len(b):
        if a[i] <= b[j]:
            result.append(a[i])
            i += 1
        else:
            result.append(b[j])
            j += 1
    while i < len(a):
        result.append(a[i])
        i += 1
    while j < len(b):
        result.append(b[i])
        j += 1
    return result
```

- **예시 테스트케이스**
  - `a = [1, 3, 5]`, `b = [2, 4, 6]` → `[1, 2, 3, 4, 5, 6]`
  - `a = []`, `b = [1, 2]` → `[1, 2]`
  - `a = [1, 2]`, `b = [3, 4]` → `[1, 2, 3, 4]`

- **테스트 실행 코드**
```python
print(solution([1, 3, 5], [2, 4, 6]))
print(solution([], [1, 2]))
print(solution([1, 2], [3, 4]))
```

---

### 문제 9 (디버깅) – 봉우리 개수

- **문제 설명**  
  정수 리스트 `nums`에서, 양 끝을 제외한 인덱스 `i`에 대해 `nums[i]`가 양 옆보다 **엄격하게 큰** 위치를 봉우리라고 할 때, 봉우리 개수를 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 봉우리 개수(정수)

- **코드 (디버깅)**

```python
def solution(nums):
    if len(nums) < 3:
        return 0
    count = 0
    for i in range(1, len(nums)):
        if nums[i] > nums[i - 1] and nums[i] > nums[i + 1]:
            count += 1
    return count
```

- **예시 테스트케이스**
  - `[1, 3, 2, 4, 1]` → `2`
  - `[1, 2, 3, 4, 5]` → `0`
  - `[5, 2, 5, 2, 5]` → `2`

- **테스트 실행 코드**
```python
print(solution([1, 3, 2, 4, 1]))
print(solution([1, 2, 3, 4, 5]))
print(solution([5, 2, 5, 2, 5]))
```

---

### 문제 10 (디버깅) – 비감소 연속 구간 최대 길이

- **문제 설명**  
  정수 리스트 `nums`에서, `nums[i] <= nums[i+1]`을 만족하는 **가장 긴 연속 부분 수열**의 길이를 반환하는 `solution` 함수입니다. 아래 코드를 한 줄만 수정하여 예시와 같이 동작하도록 하세요.

- **함수 설명**
  - 매개변수: `nums` (정수 리스트)
  - 반환값: 최대 비감소 연속 구간 길이(정수)

- **코드 (디버깅)**

```python
def solution(nums):
    if not nums:
        return 0
    best = 1
    current = 1
    for i in range(1, len(nums)):
        if nums[i] >= nums[i - 1]:
            current += 1
        else:
            current = 0
        if current > best:
            best = current
    return best
```

- **예시 테스트케이스**
  - `[1, 2, 2, 1, 3]` → `3`
  - `[5, 4, 3, 2, 1]` → `1`
  - `[1, 1, 1, 1]` → `4`

- **테스트 실행 코드**
```python
print(solution([1, 2, 2, 1, 3]))
print(solution([5, 4, 3, 2, 1]))
print(solution([1, 1, 1, 1]))
```

---

위 10문제는 행렬 연산과 조금 더 복잡한 로직을 다루며,  
import 없이 기본 문법만으로 풀 수 있도록 구성했습니다.  
빈칸을 채우고 버그를 수정하여 예시와 같은 결과가 나오도록 완성해 보세요.
