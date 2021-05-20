# Linear Search

Goal: Find a particular value in an array.
> 리스트에서 특정한 값을 찾는 알고리즘, 리스트에서 찾고자 하는 값을 맨 앞에서부터 끝까지 차례대로 찾아 나가는 것. 검색할 리스트의 길이가 길면 비효율적이지만, 검색 방법 중 가장 단순하여 구현이 쉽고 정렬되지 않은 리스트에서도 사용할 수 있다는 장점이 있다.

We have an array of generic objects. With linear search, we iterate over all the objects in the array and compare each one to the object we're looking for. If the two objects are equal, we stop and return the current array index. If not, we continue to look for the next object as long as we have objects in the array.

## An example

Let's say we have an array of numbers `[5, 2, 4, 7]` and we want to check if the array contains the number `2`.

We start by comparing the first number in the array, `5`, to the number we're looking for, `2`. They are obviously not the same, and so we continue to the next array element.

We compare the number `2` from the array to our number `2` and notice they are equal. Now we can stop our iteration and return 1, which is the index of the number `2` in the array.

## The code

Here is a simple implementation of linear search in Swift:

```swift
func linearSearch<T: Equatable>(_ array: [T], _ object: T) -> Int? {
  for (index, obj) in array.enumerated() where obj == object {
    return index
  }
  return nil
}
```

Put this code in a playground and test it like so:

```swift
let array = [5, 2, 4, 7]
linearSearch(array, 2) 	// This will return 1
```

## Performance

Linear search runs at **O(n)**. It compares the object we are looking for with each object in the array and so the time it takes is proportional to the array length. In the worst case, we need to look at all the elements in the array.

The best-case performance is **O(1)** but this case is rare because the object we're looking for has to be positioned at the start of the array to be immediately found. You might get lucky, but most of the time you won't. On average, linear search needs to look at half the objects in the array.

## See also

[Linear search on Wikipedia](https://en.wikipedia.org/wiki/Linear_search)

*Written by [Patrick Balestra](http://www.github.com/BalestraPatrick)*
