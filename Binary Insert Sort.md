Standard insert sort is:
1. for each index i>0, assume previous sub array is already sorted.
2. then for sub array before i, find a place where element at i is in correct postion, during this process need compare elements before i and swap them if not in correct order, until previous element <= element at i, this require O(n^2) comparisons and O(n^2) swaps.

```java
    public void insertSort(int from, int to) {
        for (int i=from+1; i from; j--) {
                if(arr[j-1] > arr[j]) swap(j-1, j);
                else break;
            }
        }
    }
```


Binary insert sort is an optimization, instead of sequentially compare to find correct place, before assuming array before i is sorted, so we can do binary search to find the position, reduce comparisons to O(n*log(n))
```java
  void binaryInsertSort(int from, int to) {
    binaryInsertSort(from, to, from + 1);
  }

  void binaryInsertSort(int from, int to, int i) {
    for ( ; i < to; ++i) {
      pivotIndex = i;
      int l = from;
      int h = i - 1;
      while (l <= h) {
        final int mid = (l + h) >>> 1;
        final int cmp = compare(pivotIndex, mid);
        if (cmp < 0) {
          h = mid - 1;
        } else {
          l = mid + 1;
        }
      }
      // after unsuccessful search, index l is the insert point
      for (int j = i; j > l; --j) {
        swap(j - 1, j);
      }
    }
  }
```


