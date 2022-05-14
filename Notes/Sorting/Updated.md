# Sorting

- Insertion Sort
- Selection Sort
- Bubble Sort

```C
#include<stdio.h>
#include<conio.h>
void Insertion_Sort(int arr[],int n){
    int i,j,temp;
    for(i=1;i<n;i++){
        temp=arr[i];
        for(j=i-1;j>=0 && arr[j]>temp;j--){
            arr[j+1]=arr[j];
        }
        arr[j+1]=temp;
    }
}
```

```C
void Insertion_Sort(int arr[],int n){
    int i,j,temp;
    for(i=1;i<n;i++){
        temp=arr[i];
        for(j=i-1;j>=0;j--){
            if (arr[j]>temp){
            arr[j+1]=arr[j];
            }
        }
        arr[j+1]=temp;
    }
}
```
```C
void Selection_Sort(int arr[],int n){
    int i,j,temp,min;
    for(i=0;i<n;i++){
        min=i;
        for(j=i+1;j<n;j++){
            if (min>arr[j]){
            min=arr[j];
        }
        }
        temp=arr[i];
        arr[i]=arr[min];
        arr[min]=temp;
    }
}
```
```C
void Bubble_Sort(int arr[],int n){
    int i,j,temp;
    for(i=0;i<n;i++){
        for(j=0;j<(n-i-1);j++){
            if (arr[j+1]<arr[j]){
                temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
    }
}
```
```C
void main(){
    int arr[100],i,n;
    // printf("Enter number of elements to be inserted in the array");
    // scanf("%d",&n);
    printf("Enter 5 elements in the array:\n");
    for(i=0;i<5;i++){
        scanf("%d",&arr[i]);
    }
    printf("Array elements before sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",arr[i]);
    }
    Insertion_Sort(A,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",arr[i]);
    }
    Selection_Sort(arr,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",arr[i]);
    }
    Bubble_Sort(arr,5);
    printf("\nArray elements after sorting\n");
    for(i=0;i<5;i++){
        printf("%d ",arr[i]);
    }
    getch();
}
```
## Searching
- Linear/ Sequential Search
- Binary Search
- Sorting 
    - Insertion
    - Selection
    - Bubble

```C
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>

int linear_search(int arr[],int n,int item){
    for(int i=0;i<n;i++){
        if (arr[i]==item)
        return i;
    }
    return -1;
}

int binary_search(int arr[],int i,int j,int item){
    if(i<=j){
        int mid=(i+j)/2;
        if (arr[mid]==item)
        return mid;
        else if (arr[mid]<item)
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
    int temp,min;
    for(int i=0;i<n;i++){
        min=i;
        for(int j=i;j<n;j++){
            if (arr[j]<arr[min]){
                min=j;
            }
        }
        temp=arr[i];
        arr[i]=arr[min];
        arr[min]=temp;
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
    int arr[100],n,i;
    printf("Enter size of the array\n");
    scanf("%d",&n);
    printf("Enter array elements\n");
    for(i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    printf("\nArray is:\n");
    for(i=0;i<n;i++){
        printf("%d\t",arr[i]);
    }
    int val,ind;
    printf("Enter value and index of the element to be inserted\n");
    scanf("%d %d",&val,&ind);
    for(i=n-1;i>=ind;i++){
        arr[i+1]=arr[i];
    }
    arr[ind]=val;
    n+=1;

    printf("\nArray is:\n");
    for(i=0;i<n;i++){
        printf("%d\t",arr[i]);
    }

    printf("\nEnter index of the element to be deleted\n");
    scanf("%d",&ind);
    for(i=ind;i<n-1;i++){
        arr[i]=arr[i+1];
    }
    n=n-1;

    printf("\nArray is:\n");
    for(i=0;i<n;i++){
        printf("%d\t",arr[i]);
    }

    printf("Enter the value to be searched in the array\n");
    int item;
    scanf("%d",&item);
    int flag=linear_search(arr,n,item);
    if (flag!=-1)
    printf("Element is found at %d index",flag);
    else
    printf("\nElement not present");

    bubble_sort(arr,n);
    printf("\nArray is:\n");
    for(i=0;i<n;i++){
        printf("%d\t",arr[i]);
    }
    return 0;
}
```

## 2D Array

```C
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

```C
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
        printf("Enter Student's name,roll no, sap id, phone no:\n");
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

```C
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

## Linked List Implimentation

```C
#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

typedef struct node
{
    int data;
    struct node *next;
}node;

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
        c=c+1;
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

        // Alternative
        // node *r;
        // r = head2;
        // while (r->next != NULL)
        // {
        //     r = r->next;
        // }
        // r->next = head1;
        // return head2;


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
    printf("Deleted element is %d", q->next->data);
    q->next = q->next->next;
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
    printf("Deleted element is %d", q->next->data);
    q->next = q->next->next;
    return head;
}

int main()
{
    node *head,*head2;
    int x, key, loc;
    int choice;
    do
    {
        printf("1:Create Linked List\t 2:Display\t 3:Count\t 4:Insert beginning\t 5:Insert at the end\t 6:Insert key\t 7:Insert at the location location\t 8:Delete at the beginning\t 9:Delete end\t  10:Delete key\t11:Delete loc\t 12:Create 2nd Linked List\t 13:Display 2nd Linked List\t 14:Concat 1 and 2 Linked List\t 15:item to be searched:\n");
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

## Queue Implimentation
### 1. Using Linked List

```C
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
        // Or
        // q->rear = q->rear->next;
    }

}

int dequeue(queue *q){
    int a=(q->front)->data;
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
        printf("Enter 1:Enqueue 2:Dequeue 3:Display 4:Exit\n");
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

### 2. Using Array

```C
#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

typedef struct queue
{
    int data[100];
    int front, rear;
} queue;

void init(queue *q)
{
    q->front = q->rear = -1;
}

void enqueue(queue *q)
{
    int x;
    scanf("%d", &x);
    if (q->rear == -1)
    {
        q->front = q->rear = 0;
    }
    else
        q->rear += 1;
    q->data[q->rear] = x;
}

int dequeue(queue *q)
{
    int x = q->data[q->front];
    if (q->front == q->rear)
        q->rear = q->front = -1;
    else
        q->front += 1;
    return x;
}

void display(queue *q)
{
    for (int i = q->front; i <= q->rear; i++)
    {
        printf("%d\t", q->data[i]);
    }
    printf("\n");
}

void isfull(queue *q){
    if (q->rear == 99)// MAX-1
    {
        return 1;
    }
    return 0;
}

void isempty(queue *q){
    if (q->rear == -1)
    {
        return 1;
    }
    return 0;
}

int main()
{
    int choice;
    queue q;
    init(&q);
    do
    {
        printf("Enter 1:Enqueue\t 2:Dequeue\t 3:Display\t 4:Exit:\n");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            if (q.rear != 99)
                enqueue(&q);
            else
                printf("Overflow\n");
            break;
        case 2:
            if (q.rear != -1 || q.front !=-1)
                printf("%d\n", dequeue(&q));
            else
                printf("Underflow\n");
            break;
        case 3:
            display(&q);
            break;
        case 4:
            exit(0);
            break;
        }
    } while (choice != 4);
    return 0;
}
```

## Doubly Linked List

```C
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
        head=p=q;
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


## Topics

- Address Calculation 
    - 1d
    - 2d
        - Row Major Order
        - Column Major Order
- Stack
- Expression Conversion
    - Tabular Method
    - Algorithmic Method
    - Infix to Postfix, Prefix
- Dynamic Memory Allocation
    - malloc()
    - calloc()
    - realloc()
    - free()

- Linked List
- Singly/ Simple LL
- Circular LL
- Doubly LL
- Circular Doubly LL
- Queue
```
front = rear-1 (Queue is empty)
front = rear (One element)
rear = rear+1 (After insertion)
front = front+1 (After deletion)
rear = MAX -1 (Queue is full)
rear =1 || front ==-1 (Queue is empty)
```

```C
# define MAX 100
typedef struct Queue
{
    int data[MAX];
    int R,F;
}Queue;

```
- Graphs
    - Weighted Graphs
    - Unweighted Graphs
    - Directed Graphs
    - Undirected Graphs
    - Connected Graph
    - Complete Graph
    - Sub Graph
    - Paths
    - Cycles
    - Degree of vertex
        - Indegree
        - Outdegree
    - Representation of Graphs
        - Adjacency List Representation
        - Adjacency Matrix Representation
    - Graph Traversal
        - BFS
        - DFS

- Trees
    - Binary Tree
        - Representation using Array
        - Representation using Linked List
        - Complete Binary Tree
            - BT Traversal
            - Inorder (LNR)
            - Postorder (LRN)
            - Preorder (NLR)
        - Contruct using preorder and inorder
    - AVL Tree
    - Spanning Tree
        - Minimal Spanning Tree/ Minimum Cost Spanning Tree (MST)
            - Prims
            - Kruskal
