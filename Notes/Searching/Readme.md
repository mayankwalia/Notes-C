# Searching

## Linear Search

```C
#include <stdio.h>
int linearsearch(int p[], int n, int x) {
  int i;
  for (i = 0; i <= n; i++) {
    if (p[i] == x)
      return i;
  }
  return -1;
}
int main(void) {
  int A[10], i, loc, item;
  printf("Enter 10 elements in the array\n");
  for (i = 0; i < 10; i++) {
    scanf("%d", &A[i]);
  }
  printf("Enter the element to be searched (desired element)\n");
  scanf("%d", &item);
  loc = linearsearch(A, 10, item);
  if (loc == -1)
    printf("Element is not found!\n");
  else
    printf("Element is found at %dth location\n", loc + 1);
  return 0;
}
```

## Binary Search

```C
#include <stdio.h>
int binarysearch(int p[], int i, int j, int x) {
  int mid;
  if (i <= j) {
    mid = (i + j) / 2;
    if (p[mid] == x)
      return mid;
    if (x > p[mid])
      return binarysearch(p, mid + 1, j, x);
    return binarysearch(p, i, mid - 1, x);
  }
  return -1;
}
int main(void) {
  int A[10], i, loc, item;
  printf("Enter 10 elements in the array\n");
  for (i = 0; i < 10; i++) {
    scanf("%d", &A[i]);
  }
  printf("Enter the element to be searched (desired element)\n");
  scanf("%d", &item);
  loc = binarysearch(A, 0, 9, item);
  if (loc == -1)
    printf("Element is not found!\n");
  else
    printf("Element is found at %dth location\n", loc + 1);
  return 0;
}
```
