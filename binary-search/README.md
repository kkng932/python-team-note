이진 탐색 *Binary Search*
===============================
**내부 데이터가 정렬되어 있다면 매우 빠르게 데이터를 찾을 수 있는 알고리즘**

 1. 중간점 = (시작점 + 끝점), 중간점과 찾으려는 데이터를 비교한다. 
 2. 찾으려는 데이터가 작으면 끝점 = 중간점 - 1, 크면 시작점 = 중간점 + 1 하여 중간점을 재설정한다.
 3. 찾으려는 데이터와 중간점이 일치할 때 까지 2를 반복한다. 
 4. 시작점이 끝점보다 커지면 찾으려는 데이터가 없으므로 끝낸다. 

 코딩 테스트에서 단골로 나오는 문제이니 가급적 외우기
 
 시간복잡도: O(logN)
```python
def binary_search(array, target, start, end):
    while start <= end:
        mid = (start + end) // 2
        if array[mid] == target:
            return mid + 1
        elif array[mid] > target:
            end = mid - 1
        else:
            start = mid + 1
    return None


n, target = list(map(int, input().split()))
array = list(map(int, input().split()))

result = binary_search(array, target, 0, n - 1)
if result == None:
    print("원소가 존재하지 않습니다.")
else:
    print(result)

```
