# 거품 정렬 (Bubble Sort)

*Assembled by Ricky (2019-10-29)*

<br>

## Goal

- Bubble Sort에 대해 설명할 수 있다.
- Bubble Sort 과정에 대해 설명할 수 있다.
- Bubble Sort을 구현할 수 있다.
- Bubble Sort의 시간복잡도와 공간복잡도를 계산할 수 있다.

<br>

## Abstract

Bubble Sort는 Selection Sort와 유사한 알고리즘으로 **```서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘```** 입니다.

이름의 유래로는 정렬 과정에서 원소의 이동이 거품이 수면으로 올라오는 듯한 모습을 보이기 때문에 지어졌다고 합니다.

<br>

## Process (Ascending)

1. 1회전에 첫 번째 원소와 두 번째 원소를, 두 번째 원소와 세 번째 원소를, 세 번째 원소와 네 번째 원소를, … 이런 식으로  (마지막-1)번째 원소와 마지막 원소를 비교하여 조건에 맞지 않는다면 서로 교환합니다.
2. 1회전을 수행하고 나면 가장 큰 원소가 맨 뒤로 이동하므로 2회전에서는 맨 끝에 있는 원소는 정렬에서 제외되고, 2회전을 수행하고 나면 끝에서 두 번째 원소까지는 정렬에서 제외됩니다. 이렇게 정렬을 1회전 수행할 때마다 정렬에서 제외되는 데이터가 하나씩 늘어납니다.

<br>

## Java Code (Ascending)

```java
void bubbleSort(int[] arr) {
    int temp = 0;
	for(int i = 0; i < arr.length; i++) {       // 1.
		for(int j= 1 ; j < arr.length-i; j++) { // 2.
			if(arr[j-1] > arr[j]) {             // 3.
                // swap(arr[j-1], arr[j])
				temp = arr[j-1];
				arr[j-1] = arr[j];
				arr[j] = temp;
			}
		}
	}
	System.out.println(Arrays.toString(arr));
}
```

1. 제외될 원소의 갯수를 의미합니다. 1회전이 끝난 후, 배열의 마지막 위치에는 가장 큰 원소가 위치하기 때문에 하나씩 증가시켜줍니다.
2. 원소를 비교할 index를 뽑을 반복문입니다. j는 현재 원소를 가리키고, j-1은 이전 원소를 가리키게 되므로, j는 1부터 시작하게 됩니다.
3. 현재 가르키고 있는 두 원소의 대소를 비교합니다. 해당 코드는 오름차순 정렬이므로 현재 원소보다 이전 원소가 더 크다면 이전 원소가 뒤로 가야하므로 서로 자리를 교환해줍니다.

<br>

## GIF로 이해하는 Bubble Sort

<img src="./resources/bubble-sort-001.gif">

<br>

## 시간복잡도 & 공간복잡도

- 시간복잡도
  - 시간복잡도를 계산하면, ```(n-1) + (n-2) + (n-3) + .... + 2 + 1 => n(n-1)/2```이므로, O(n^2)입니다.  또한, Bubble Sort는 정렬이 돼있던 안돼있던, 2개의 원소를 비교하기 때문에 최선, 평균, 최악 모두 시간복잡도가 **O(n^2)** 으로 동일합니다. *(개선된 Bubble Sort가 존재하긴 하나, 이번 장은 기초를 다지기 위한 학습이므로 넘어가겠습니다.)*

- 공간복잡도
  - 주어진 배열 안에서 교환(swap)을 통해, 정렬이 수행되므로 **O(n)** 입니다.

<br>

## 장점

- 구현이 매우 간단하고, 소스코드가 직관적입니다.
- 정렬하고자 하는 배열 안에서 교환하는 방식이므로, 다른 메모리 공간을 필요로 하지 않습니다. => 제자리 정렬(in-place sorting)
- 안정 정렬(Stable Sort) 입니다.

<br>

## 단점

- 시간복잡도가 최악, 최선, 평균 모두 O(n^2)으로, 굉장히 비효율적입니다.
- 정렬 돼있지 않은 원소가 정렬 됐을때의 자리로 가기 위해서, 교환 연산(swap)이 많이 일어나게 됩니다.

<br>

## Conclusion

정렬 알고리즘 중에 가장 직관적인 Bubble Sort에 대해 알아보았습니다. 기술 면접에서도 종종 나오는 정렬 알고리즘으로 알아두시면 좋을 것 같습니다.

<br>


## Reference & Additional Resources

- https://zeddios.tistory.com/20 
- https://jinhyy.tistory.com/9 
- https://gmlwjd9405.github.io/2018/05/06/algorithm-bubble-sort.html 




