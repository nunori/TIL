# 이진 탐색

> *이진 탐색* : 정렬이 되어 있는 배열에서 특정한 값을 찾는 알고리즘

배열에서의 이진 탐색은 특정 값에 대한 *배열의 특정 인덱스*를 찾기 위함이다.

정렬이 되어 있지 않을 경우 정렬하는 과정을 거친 후 이진 탐색을 진행해야 한다.

이진 탐색은 탐색을 할 때마다 범위를 반씩 줄여나가기 때문에 선형 탐색보다 탐색 속도가 빠르며 그렇기 때문에 이진 탐색의 시간 복잡도는 O(log n)이 된다.

배열의 중간 값을 선택하여 찾고자 하는 값과 비교한다.

중간 값이 찾고자 하는 값보다 크다면 중간을 기준으로 오른쪽에서 탐색하며 찾고자 하는 값보다 작다면 중간을 기준으로 왼쪽에서 탐색한다.

```
// 재귀로 구현
// low : 첫 번째 인덱스
// high : 마지막 인덱스
// key : 찾고자 하는 값
int binarySearch(int key, int low, int high) {
		int mid;
		
		if(low <= high) {
			mid = (low + high) / 2;
			
			if(key == arr[mid]) 
				return mid;
			 else if (key < arr[mid]) 
				return binarySearch(key, low, mid-1);
			 else 
				return binarySearch(key, mid + 1, high);
			
		}
		return -1;
	}
```
또는 
```
// 반복문으로 구현
// low : 첫 번째 인덱스
// high : 마지막 인덱스
// key : 찾고자 하는 값
int binarySearch(int key, int low, int high) {
		int mid;
		
		while(low <= high) {
			mid = (low + high) / 2;
					
			if(key == arr[mid])
				return mid;
			else if (key < arr[mid])
				high = mid - 1;
			else
				low = mid + 1;
		}
		return -1;
	}
```
