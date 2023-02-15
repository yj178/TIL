# 이진 탐색이란?
이진 탐색(Binary Search)은 **정렬된 배열**에서 원하는 값을 빠르게 찾기 위한 탐색 알고리즘입니다. 배열의 중간 값과 비교하여 탐색 범위를 반씩 줄이므로 시간 복잡도는 $O(log_2N)$입니다.

# 이진 탐색 활용 사례
이진 탐색은 대용량 데이터베이스나 검색 엔진에서 매우 효율적으로 사용됩니다. 예를 들어, 주민번호나 운전면허번호 등 고유한 번호를 기준으로 정렬된 데이터에서 특정 번호를 찾을 때 이진 탐색이 사용됩니다.

# 이진 탐색 활용 문제 링크
[1920] 수 찾기: 주어진 수열에서 특정 수가 존재하는지 찾는 문제로, 이진 탐색을 활용하여 해결할 수 있습니다.

[1654] 랜선 자르기: 길이가 제각각인 여러 개의 랜선에서 N개의 같은 길이의 랜선을 만들기 위해 잘라야 하는 길이의 최댓값을 구하는 문제로, 이진 탐색을 사용하여 해결할 수 있습니다.

# 자바 라이브러리의 이진 탐색
아래 코드는 자바의 표준 라이브러이 `Arrays.binarySearch()`입니다.
```java
private static int binarySearch0(long[] a, int fromIndex, int toIndex,
                                     long key) {
        int low = fromIndex;
        int high = toIndex - 1;

        while (low <= high) {
            int mid = (low + high) >>> 1;
            long midVal = a[mid];

            if (midVal < key)
                low = mid + 1;
            else if (midVal > key)
                high = mid - 1;
            else
                return mid; // key found
        }
        return -(low + 1);  // key not found.
    }
```


## 이진 탐색 구현시 참고 사항
이진 탐색은 정렬된 배열에서 특정 값을 찾는 것 외에도, 주어진 값과 일치하지 않는 가장 작은 수(lower bound)와 가장 큰 수(upper bound)를 찾는 데에도 활용됩니다.

Lower bound는 배열에서 주어진 값 이상인 가장 작은 인덱스를 찾는 것이고, upper bound는 배열에서 주어진 값보다 큰 가장 작은 인덱스를 찾는 것입니다. 이 두 값은 일반적으로 이진 탐색 알고리즘을 이용해 효율적으로 구할 수 있습니다.
