# Sorting

- Insertion Sort
- Selection Sort
- Bubble Sort

```
#include<stdio.h>
#include<conio.h>
void Insertion_Sort(int A[],int x){
    int i,j,temp;
    for(i=1;i<x;i++){
        temp=A[i];
        for(j=i-1;j>=0 && A[j]>temp;j--){
            A[j+1]=A[j];
        }
        A[j+1]=temp;
    }
}
void Selection_Sort(int A[],int x){
    int i,j,temp,min,idx;
    for(i=0;i<x;i++){
        min=A[i];
        idx=i;
        for(j=i+1;j<x;j++){
            if (min>A[j]){
            min=A[j];
            idx=j;
        }
        }
        temp=A[i];
        A[i]=A[idx];
        A[idx]=temp;
    }
}
void Bubble_Sort(int A[],int x){
    int i,j,temp;
    for(i=0;i<x;i++){
        for(j=0;j<(x-i-1);j++){
            if (A[j+1]<A[j]){
                temp=A[j];
                A[j]=A[j+1];
                A[j+1]=temp;
            }
        }
    }
}
void main(){
    int A[5],i;
    printf("Enter 5 elements in the array:\n");
    for(i=0;i<5;i++){
        scanf("%d",&A[i]);
    }
    printf("Array elements before sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",A[i]);
    }
    Insertion_Sort(A,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",A[i]);
    }
    Selection_Sort(A,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",A[i]);
    }
    Bubble_Sort(A,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",A[i]);
    }
    getch();
}
```
