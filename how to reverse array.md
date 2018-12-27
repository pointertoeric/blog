Suppose there is an array, ```arr```, how do you inverse the the array between index ```from``` and ```to```, here ```to``` is exclusive?

This is a simple algorithm problem, just need to maintain two pointers to ```from``` and ```to```, swap the array element, then increase and decrease them.

```java
final void reverse(int from, int to) {
    for (--to; from < to; ++from, --to) {
      swap(from, to);
    }
  }
```

