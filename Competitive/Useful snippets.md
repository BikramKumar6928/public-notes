#competetive #notes
# To get the size of an array

```C++
int a[];
int length = sizeof(a)/sizeof(a[0]);
```

**Note**:- This only works if the array has not been passed through a function. If it is passed through a function, an `int[]`(int array) becomes an `int*` (int pointer), thus losing it's data as an array.

More information :- https://www.geeksforgeeks.org/using-sizof-operator-with-array-paratmeters/