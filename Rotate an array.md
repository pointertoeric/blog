The problem is given an array, e.g.
```[1, 2, 3, 4, 5],  index lo=0, hi=5(exclusive), mid=2```, rotate the array around index 2, so after rotate, it will be:
```[3, 4, 5, 1, 2]```

to solve it, need 3 reverse operations:
1. reverse array[lo, mid]
2. reverse array[mid, hi]
3. reverse array[lo, hi]

<script src="https://gist.github.com/pointertoeric/f699f74ea4e7eef8d29f79b6d96372b4.js"></script>
