https://www.angelcode.com/angelscript/sdk/docs/manual/doc_datatypes_arrays.html

```c
// A zero-length array of integers
  int[] a;
  array<int> a;
  
// An array of integers with 3 elements
  int[] b(3);
  array<int> b(3);

// An array of integers with 3 elements, all set to 1 by default
  int[] c(3, 1);
  array<int> c(3, 1);
  
// An array of integers with 3 elements with specific values
  int[] d = {5,6,7};
  array<int> d = {5,6,7};

// An empty array of arrays of integers
  int[][] a;
  array<array<int>> a;

// A 2 by 2 array with initialized values
  int[][] b =  {{1,2},{3,4}};
  array<array<int>> b = {{1,2},{3,4}};

// A 10 by 10 array of integers with uninitialized values
  int[][] c(10, int[](10));
  array<array<int>> c(10, array<int>(10));
  
```


