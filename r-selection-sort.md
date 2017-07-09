# 데이터 과학을 위한 R 알고리즘


## 1. 선택 정렬

[Sorting algorithms/Selection sort](http://rosettacode.org/wiki/Sorting_algorithms/Selection_sort#R)에 R로 구현한 선택정렬 알고리즘이 두개 있다.
하나는 루프를 돌려 선택정렬하는 방식이고, 다른 한 방식은 재귀를 활용한 방식이다.

### 1.1. R 선택정렬 (재귀)

가장 먼저 재귀를 이용한 방식은 선택정렬을 이해하기 쉬운데, 벡터에서 최소값을 잡아 새로 만드는 벡터처음에 넣고,
최소값을 벡터에서 제외한다. 최소값이 하나 제외된 벡터를 다시 반복을 돌려 그 다음 최소값을 위치시키는 방식으로 벡터를 정렬시킨다.


```r
vec <- c(5, 3, 6, 2, 10)
## 1. 재귀를 활용한 선택정렬
selection_sort_recursion <- function(vec)
{
  if(length(vec) > 1)
  {
    mini <- which.min(vec)
    c(vec[mini], selection_sort_recursion(vec[-mini]))
  } else return(vec)
}

selection_sort_recursion(vec)
```

```
## [1]  2  3  5  6 10
```

### 1.2. R 선택정렬 (함수)

두번째 함수를 이용한 방법은 벡터의 최소값을 찾는 함수를 구현하여 최소값을 찾아내고, 
이를 본 함수에서 새로 만든 벡터(`new_vec`)에 하나씩 추가해 나가는 방식이다. 물론, 찾아진 최소값을 벡터에서 제거시키고 난 벡터를 
다시 선택정렬 알고리즘에 넣어 반복하면 정렬된 벡터가 차곡차곡 `new_vec`에 정렬된다.


```r
## 2. 함수를 활용한 방법
find_smallest <- function(vec) {
  smallest <- vec[1]
  smallest_index <- 1
  for(i in seq_along(vec)) {
    if (vec[i] < smallest) {
      smallest <- vec[i]
      smallest_index <- i
    }
  }
  return(smallest_index)
}

selection_sort_python <- function(vec) {
  new_vec <- NULL
  for(i in seq_along(vec)) {
    smallest <- find_smallest(vec)
    new_vec[i] <-vec[smallest]
    vec <- vec[-smallest]
  }
  return(new_vec)
}

selection_sort_python(vec)
```

```
## [1]  2  3  5  6 10
```

### 1.3. R 선택정렬 (루프)

세번째 선택정렬 알고리즘은 상대적으로 간결한 대신에 읽기가 쉽지 않다.
최소값을 갖는 벡터 인덱스를 `mini`로 놓고, 루프를 돌리면서 벡터 크기를 하나씩 줄여나가고,
최소값을 찾은 벡터를 새로운 벡터에 넣어 선택정렬한다.


```r
## 2. 루프를 돌리는 선택정렬
selection_sort <- function(vec)
{
  lenx <- length(vec)
  for(i in seq_along(vec))
  {
    mini <- (i - 1) + which.min(vec[i:lenx])
    start_ <- seq_len(i-1)
    vec <- c(vec[start_], vec[mini], vec[-c(start_, mini)])
  }
  return(vec)
}

# 이진 검색 실행
selection_sort(vec)
```

```
## [1]  2  3  5  6 10
```

### 1.2. 파이썬 코드

파이썬 코드를 R 선택정렬 (함수)로 시각화하면 다음과 같다.
즉, 최소값을 찾아 이를 순차적으로 하나씩 새로운 벡터에 아무것도 남지 않을 때까지 집어 넣어 정렬작업을 완료한다.

<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=%23%20Finds%20the%20smallest%20value%20in%20an%20array%0Adef%20findSmallest%28arr%29%3A%0A%20%20%23%20Stores%20the%20smallest%20value%0A%20%20smallest%20%3D%20arr%5B0%5D%0A%20%20%23%20Stores%20the%20index%20of%20the%20smallest%20value%0A%20%20smallest_index%20%3D%200%0A%20%20for%20i%20in%20range%281,%20len%28arr%29%29%3A%0A%20%20%20%20if%20arr%5Bi%5D%20%3C%20smallest%3A%0A%20%20%20%20%20%20smallest%20%3D%20arr%5Bi%5D%0A%20%20%20%20%20%20smallest_index%20%3D%20i%0A%20%20return%20smallest_index%0A%0A%23%20Sort%20array%0Adef%20selectionSort%28arr%29%3A%0A%20%20newArr%20%3D%20%5B%5D%0A%20%20for%20i%20in%20range%28len%28arr%29%29%3A%0A%20%20%20%20%20%20%23%20Finds%20the%20smallest%20element%20in%20the%20array%20and%20adds%20it%20to%20the%20new%20array%0A%20%20%20%20%20%20smallest%20%3D%20findSmallest%28arr%29%0A%20%20%20%20%20%20newArr.append%28arr.pop%28smallest%29%29%0A%20%20return%20newArr%0A%0Aprint%20selectionSort%28%5B5,%203,%206,%202,%2010%5D%29%0A&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=79&heapPrimitives=false&origin=opt-frontend.js&py=2&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>



