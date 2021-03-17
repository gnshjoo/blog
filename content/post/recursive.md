+++
title = "재귀 알고리즘 (이진탐색) "
date = 2021-03-17T14:57:54+09:00
tags = ["알고리즘"]
description = ""
featuredImage = ""
draft = false
+++
재귀 알고리즘의 유용성
- 사람이 생가하는 방식을 코드로 옮길 수 있기 때문에 유용한 면이 있다. ex) 하노이의 탑

재귀 단점
- 효율적이지 않다..?!

리스트 L과, 그 안에서 찾으려 하는 원소 x 가 인자로 주어지고, 또한 탐색의 대상이 되는 리스트내에서의 범위 인덱스가 lower 부터 upper 까지로 (인자로) 정해질 때, x와 같은 값을 가지는 원소의 인덱스를 리턴하는 함수를 완성하세요. 만약 리스트 L 안에 x 와 같은 값을 가지는 원소가 존재하지 않을 경우에는 -1 을 리턴합니다. 리스트 L 은 자연수 원소들로 이루어져 있으며, 크기 순으로 정렬되어 있다고 가정합니다. 또한, 동일한 원소는 두번 이상 나타나지 않습니다

```python
# 재귀 이진 탐색
def binsearch(L, x, lower, upper):
	if _____:
		return -1
	mid = (lower + upper) //2
	if x == L[mid]:
		return mid
	elif x < L[mid]:
		return _____
	else:
		return _____
```

```python
def binsearch(L, x, lower, upper):
	if lower > upper:
		return -1
	mid = (lower + upper ) //2
	if x == L[mid]:
		return mid
	elif x < L[mid]:
		return binsearch(L, x, mid+1, upper)
	else:
		return binsearch(L, x, lower, mid-1)
```