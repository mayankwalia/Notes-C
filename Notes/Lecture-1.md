# Day 1: C DSA
## Questions:
1. Hello world
2. Array input and output
3. Print only odd/even elements of the Array
4. Print sum of even and odd elements in the Array

---
## Points to be noted:
### Taking input
```
scanf("%d",&variable_name);
```
### Generating output
```
printf("%d",variable_name);
```

---
## Solutions
- Solution for Question 1 
```
#include <stdio.h> //c preprocessor (printf)
// #include <conio.h> //for getch function
int main(void) {
  clrscr(); //In Turbo c for clearing previous screen
  printf("Hello world");
  return 1;
}
```
- Solution for Question 2 
```
#include <stdio.h> //c preprocessor (printf)
// #include <conio.h> //for getch functions

int main(void) {
  clrscr(); //In Turbo c for clearing previous screen
  int a[5];
  int i;
  // Taking input
  printf("Enter 5 elements in the array\n");
  for(i=0;i<5;i++){
    scanf("%d",&a[i]);
  }
  // Generating output
  printf("Entered elements are:\n");
  
```
- Solution for Question 3
```
#include <stdio.h> //c preprocessor (printf)
// #include <conio.h> //for getch function
int main(void) {
  printf("Enter 5 elements in the array\n");
  for(i=0;i<5;i++){
    scanf("%d",&a[i]);
  }
  int sum_e=0,sum_o=0;
  printf("Odd elements are:\n");
  for(i=0;i<5;i++){
     printf("%d ",a[i]);
     if (a[i]%2!=0){
       printf("%d\n",a[i]);
    }
        }
  }
  }
  return 1;
}
  
```
- Solution for Question 4
```
#include <stdio.h> //c preprocessor (printf)
// #include <conio.h> //for getch function
int main(void) {

  printf("Enter 5 elements in the array\n");
  for(i=0;i<5;i++){
    scanf("%d",&a[i]);
  }
  int sum_e=0,sum_o=0;
    if (a[i]%2==0){
      sum_e+=a[i];
    }
    else{
      sum_o+=a[i];
    }
  printf("Sum of even Numbers: %d\n",sum_e);
  printf("Sum of odd Numbers: %d\n",sum_o);
  return 1;
}
}
```

# Assignments

## WAP to create array of 10 elements. print the square of each number.
```
#include<stdio.h>
int main(){
  // Array is initialized at the time of declaration
  // int a[10]={3,2,5,7,2,7,38,32,6,2}; 
  int a[10];
  int i;
  // Taking input from the user
  printf("Enter 10 array elements\n");
  for (i=0;i<10;i++){
    scanf("%d",&a[i]);
  }
  // Printing Squares
  printf("Printing squares of array elements\n");
  for (i=0;i<10;i++){
    printf("%d\t",a[i]*a[i]);
  }
  return 1;
}
```


## WAP to find average and sum of three numbers entered through keyboard.
```
#include<stdio.h>
int main(){
  int a[3];
  int i;
  // Taking three numbers as input
  printf("Enter array elements\n");
  for (i=0;i<3;i++){
    scanf("%d",&a[i]);
  }
  // Calculating sum and average
  int sum=0;
  for (i=0;i<3;i++){
    sum+=a[i];
  }
  // Displaying results
  printf("Sum of three elements is: %d\n",sum);
  float avg=(sum/3.0);
  printf("Average of three elements is: %.2f\n",avg);
  return 1;
}
```
