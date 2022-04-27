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



```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

int linear_search(int arr[],int n,int x){
    for(int i=0;i<n;i++){
        if (arr[i]==x)
        return i;
    }
    return -1;
}
int binary_search(int arr[],int i,int j,int x){
    if(i<=j){
        int mid=(i+j)/2;
        if (arr[mid]==x)
        return mid;
        else if (arr[mid]<x)
        return binary_search(arr,mid+1,j,x);
        else
        return binary_search(arr,i,mid-1,x);
    }
    else
    return -1;
}
void insertion_sort(int arr[],int n){
    int temp;
    for(int i=0;i<n-1;i++){
        for(int j=i+1;j>0;j--){
            if(arr[j]<arr[j-1]){
                temp=arr[j];
                arr[j]=arr[j-1];
                arr[j-1]=temp;
            }
            else
            break;
        }
    }    
}
void selection_sort(int arr[],int n){
    int temp,mini;
    for(int i=0;i<n;i++){
        mini=i;
        for(int j=i;j<n;j++){
            if (arr[j]<arr[mini]){
                mini=j;
            }
        }
        temp=arr[i];
        arr[i]=arr[mini];
        arr[mini]=temp;

        
    }
    
}
void bubble_sort(int arr[],int n){
    int temp;
    for(int i=0;i<n-1;i++){
        for(int j=0;j<n-i-1;j++){
            if (arr[j]>arr[j+1]){
                temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
    }
    
}

int main(){
    int i;
    int arr1[5]={6,3,7,1,8};
    selection_sort(arr1,5);
    printf("\nArray is:\n");
    for(i=0;i<5;i++){
        printf("%d\t",arr1[i]);
    }
    int arr2[5]={6,3,7,1,8};
    insertion_sort(arr2,5);
    printf("\nArray is:\n");
    for(i=0;i<5;i++){
        printf("%d\t",arr2[i]);
    }
    int arr3[5]={6,3,7,1,8};
    bubble_sort(arr3,5);
    printf("\nArray is:\n");
    for(i=0;i<5;i++){
        printf("%d\t",arr3[i]);
    }



    // int arr[100],n,i;
    // printf("Enter size of the array\n");
    // scanf("%d",&n);
    // printf("Enter array elements\n");
    // for(i=0;i<n;i++){
    //     scanf("%d",&arr[i]);
    // }
    // printf("\nArray is:\n");
    // for(i=0;i<n;i++){
    //     printf("%d\t",arr[i]);
    // }

    // int val,ind;
    // printf("Enter val and index of the element to be inserted\n");
    // scanf("%d %d",&val,&ind);
    // for(i=n-1;i>=ind;i++){
    //     arr[i+1]=arr[i];
    // }
    // arr[ind]=val;
    // n+=1;

    // printf("\nArray is:\n");
    // for(i=0;i<n;i++){
    //     printf("%d\t",arr[i]);
    // }

    // printf("\nEnter index of the element to be deleted\n");
    // scanf("%d",&ind);
    // for(i=ind;i<n-1;i++){
    //     arr[i]=arr[i+1];
    // }
    // n-=1;
    // printf("\nArray is:\n");
    // for(i=0;i<n;i++){
    //     printf("%d\t",arr[i]);
    // }
    // printf("Enter the value to be searched in the array\n");
    // int x;
    // scanf("%d",&x);
    // int flag=linear_search(arr,n,x);
    // if (flag!=-1)
    // printf("Element is found at %d index",flag);
    // else
    // printf("\nElement not present");

    // bubble_sort(arr,n);
    // printf("\nArray is:\n");
    // for(i=0;i<n;i++){
    //     printf("%d\t",arr[i]);
    // }
    return 0;
}
```

## 2D Array

```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

int main(){
    int arr[20][20],m,n;
    printf("Enter no. of rows\n");
    scanf("%d",&m);
    printf("Enter no. of cols\n");
    scanf("%d",&n);
    int i,j;
    printf("Enter elements\n");
    for(i=0;i<m;i++){
        for(j=0;j<n;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    printf("2D-Array is:\n");
    for(i=0;i<m;i++){
        for(j=0;j<n;j++){
            printf("%d\t",arr[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```


## Structure

```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

typedef struct student{
    int roll,sap;
    char name[20];
    int phone;
}student;

int main(){
    int i;
    student s[5];
    for(i=0;i<5;i++){
        printf("Enter student name,roll no, sap id, phone no:\n");
        scanf("%s%d%d%d",&s[i].name,&s[i].roll,&s[i].sap,&s[i].phone);
    }

    printf("Student details:\n");
    for(i=0;i<5;i++){
        printf("%s\t%d\t\t%d\t%d",s[i].name,s[i].roll,s[i].sap,s[i].phone);
        printf("\n");
    }
    return 0;
}
```

## Stack

```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

typedef struct stack{
    int data[100];
    int top;
}stack;

void init(stack *s){
    s->top=-1;
}

void push(stack *s){
    int x;
    printf("Enter value to be pushed:\n");
    scanf("%d",&x);
    s->top++;
    s->data[s->top]=x;
}

int pop(stack *s){
    int x=s->data[s->top];
    s->top--;
    return x;
}

void display(stack *s){
    for(int i=s->top;i>=0;i--){
        printf("%d\t",s->data[i]);
    }
    printf("\n");
}

int main(){
    stack s;
    init(&s);
    int choice;
    do{
        scanf("%d",&choice);
        switch(choice){
            case 1:
            if (s.top==99){
                printf("Overflow (Stack is full)\n");
            }
            else
            push(&s);
            break;
            case 2:
            if(s.top==-1)
            printf("Underflow (Stack is empty)\n");
            else
            printf("Deleted element is %d\n",pop(&s));
            break;
            case 3:
            if(s.top==-1)
            printf("Stack is empty\n");
            else
            display(&s);
            break;
            case 4:
            exit(0);
            }
    }while (choice!=4);
    return 0;
}
```

## Linked List

```
#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

typedef struct node
{
    int data;
    struct node *next;
} node;

void display(node *head)
{
    while (head != NULL)
    {
        printf("%d\t", head->data);
        head = head->next;
    }
}

node *create(int n)
{
    node *head, *p;
    head = (node *)malloc(sizeof(node));
    printf("Enter data");
    int x;
    scanf("%d", &x);
    head->data = x;
    head->next = NULL;
    p = head;
    for (int i = 1; i < n; i++)
    {
        p->next = (node *)malloc(sizeof(node));
        p = p->next;
        printf("Enter data");
        scanf("%d", &x);
        p->data = x;
        p->next = NULL;
    }
    return (head);
}

int count(node *head)
{
    int c = 0;
    while (head != NULL)
    {
        c++;
        head = head->next;
    }
    return c;
}

node *concat(node *head1, node *head2)
{
    if (head1 == NULL)
        return head2;
    else if (head2 == NULL)
        return head1;
    else
    {
        node *r;
        r = head1;
        while (r->next != NULL)
        {
            r = r->next;
        }
        r->next = head2;
        return head1;
    }
}

node *insertion_beg(node *head, int x)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q->data = x;
    q->data = NULL;
    if (head == NULL)
        head = q;
    else
    {
        q->next = head;
        head = q;
    }
    return head;
}
node *insertion_end(node *head, int x)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q->data = x;
    q->next = NULL;
    if (head == NULL)
        head = q;
    else
    {
        node *p;
        p = head;
        while (p->next != NULL)
        {
            p = p->next;
        }
        p->next = q;
    }
    return head;
}
node *insertion_key(node *head, int x, int key)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q->data = x;
    q->next = NULL;
    node *p;
    p = head;
    while (p->data != key && p != NULL)
    {
        p = p->next;
    }
    q->next = p->next;
    p->next = q;
    return head;
}
node *insertion_loc(node *head, int x, int loc)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q->data = x;
    q->next = NULL;
    node *p;
    p = head;
    for (int i = 0; i < loc - 1; i++)
    {
        p = p->next;
    }
    q->next = p->next;
    p->next = q;
    return head;
}
node *deletion_beg(node *head)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q = head;
    head = q->next;
    printf("Deleted node is %d", q->data);
    free(q);
    return head;
}
node *deletion_end(node *head)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q = head;
    while ((q->next)->next != NULL)
    {
        q = q->next;
    }
    printf("Deleted node is %d", (q->next)->data);
    q->next = NULL;
    free(q);
    return head;
}
node *deletion_key(node *head, int key)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q = head;
    while ((q->next)->data != key)
    {
        q = q->next;
    }
    q->next = q->next->next;
    printf("Deleted element is %d", q->next->data);
    return head;
}
node *deletion_loc(node *head, int loc)
{
    node *q;
    q = (node *)malloc(sizeof(node));
    q = head;
    for (int i = 0; i < loc - 1; i++)
    {
        q = q->next;
    }
    q->next = q->next->next;
    printf("Deleted element is %d", q->next->data);
    return head;
}

int main()
{
    node *head,*head2;
    int x, key, loc;
    int choice;
    do
    {
        printf("1:Create LL\t2:Display\t3:Count\t4:Insert beg\t5:Insert end\t6:Insert key\t7:Insert loc\t8:Del beg\t9:Del end\t10:Del key\t11:Del loc\t12:Create 2nd LL\t13:Display 2nd LL\14:Concat 1 and 2 LL\t15:item to be searched:\n");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            printf("Enter no of nodes");
            int n;
            scanf("%d", &n);
            head = create(n);
            break;
        case 2:
            display(&head);
            break;
        case 3:
            printf("Count %d", count(&head));
            break;
        case 4:
            printf("Enter x");
            scanf("%d", &x);
            head = insertion_beg(&head, x);
            break;
        case 5:
            printf("Enter x");
            scanf("%d", &x);
            head = insertion_end(&head, x);
            break;
        case 6:
            printf("Enter x");
            scanf("%d%d", &x, &key);
            head = insertion_key(&head, x, key);
            break;
        case 7:
            printf("Enter x");
            scanf("%d%d", &x, &loc);
            head = insertion_loc(&head, x, loc);
            break;
        case 8:
        head=deletion_beg(&head);
        break;
        case 9:
        head=deletion_end(&head);
        break;
        case 10:
        scanf("%d",&key);
        head=deletion_key(&head,key);
        break;
        case 11:
        scanf("%d", &loc);
        head=deletion_loc(&head,loc);
        break;
        case 12:
        printf("Enter no of nodes");
        int n;
        scanf("%d", &n);
        head2 = create(n);
        break;
        case 13:
        display(&head2);
        break;
        case 14:
        head=concat(&head,&head2);
        break;
        case 15:
        break;
        case 16:
        exit(0);
        }
    }while (choice!=16);
    
    return 0;
}
```

## Queue

### Using Linked List

```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

typedef struct node{
    int data;
    struct node *next;
}node;

typedef struct queue{
    struct node *front,*rear;
}queue;

void init(queue *q){
    q->front=q->rear=NULL;
}

void enqueue(queue *q,int x){
    node *p;
    p=(node *)malloc(sizeof(node));
    p->data=x;
    p->next=NULL;
    if (q->front==NULL)
    q->front=q->rear=p;
    else
    {
        (q->rear)->next=p;
        q->rear=p;
    }

}

int dequeue(queue *q){
    int a= (q->front)->data;
    node *r=q->front;
    if (q->front==q->rear)
    q->front=q->rear=NULL;
    else
    q->front=(q->front)->next;
    free(r);
    return a;

}

void display(queue *q){
    node *r;
    r=q->front;
    while (r!=NULL){
        printf("%d\t",r->data);
        r=r->next;
    }

}

int main(){
    queue q;
    int choice;
    do{
        printf("Enter 1 ...");
        scanf("%d",&choice);
        switch (choice){
            case 1: printf("Enter value to be inserted");
            int x;
            scanf("%d",&x);
            enqueue(&q,x);
            break;
            case 2: printf("Deleted element is %d",dequeue(&q));
            break;
            case 3: display(&q);
            break;
            case 4: exit(0);
            break;
        }
    }while (choice!=4);
    return 0;
}
```
### Using Array


## Doubly Linked List
```
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

typedef struct node
{
    int data;
    struct node *next,*prev;
}node;


node *create(int n){
    node *head,*p,*q;
    head=NULL;
    for(int i=0;i<n;i++){
        q=(node *)malloc(sizeof(node));
        printf("Enter data");
        scanf("%d",&q->data);
        q->next=NULL;
        q->prev=NULL;
        if (head==NULL)
        head=q=p;
        else
        {
            p->next=q;
            q->prev=p;
            p=p->next;
        }
    }
    return head;

}

void displayforward(node *head){
    node *q;
    q=head;
    while (q!=NULL){
        printf("%d\t",q->data);
        q=q->next;
    }
}

void displaybackward(node *head){
    node *q;
    q=head;
    while (q->next!=NULL){
        q=q->next;
    }
    while (q!=NULL){
        printf("%d\t",q->data);
        q=q->prev;
    }
}

int main(){
    node *head;
    int choice;
    int n;
    do{
        scanf("%d",&choice);
        switch (choice)
        {
        case 1:
            printf("Enter no of elements to be inserted\n");
            scanf("%d",&n);
            head=create(n);
            break;
        case 2:
        displayforward(&head);
        break;
        case 3:
        displaybackward(&head);
        break;
        case 4:
        exit(0);
        }
    }while (choice!=4);
    return 0;
}
```
