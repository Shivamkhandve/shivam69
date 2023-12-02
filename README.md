# shivam69
1. Write a program to implement circular queue using array
#include<stdio.h>
#define MAX 5
void enqueue(int x);
void dequeue();
void display();
void exit();
int queue[MAX],front=-1,rear=-1;
int main()
{
int ch,x;
while(1)
{
printf("\n1.enqueue\n2.dequeue\n3.display\n4.exit\n");
scanf("%d",&ch);
switch(ch)
{
case 1: printf("enter value to insert ");
scanf("%d",&x);
enqueue(x);
break;
case 2:dequeue();
break;
case 3:display();
break;
case 4: exit();
break;
default:printf("\nwrong choice");
}
}
}
void enqueue(int x)
{
if(front==-1&&rear==-1)
{
front=rear=0;
queue[rear]=x;
}
else if((rear+1)%MAX==front)
{
printf("queue is full");
}
else
{
rear=(rear+1)%MAX;
queue[rear]=x;
}
}
void dequeue()
{
if(front==-1&&rear==-1)
{
printf("queue is empty");
}
else if(front==rear)
{
printf("%d is deleted",queue[front]);
front=rear=-1;
}
else
{
printf("%d is deleted",queue[front]);
front=(front+1)%MAX;
}
}
void display()
{
int i=front;
if(front==-1&&rear==-1)
{
printf("queue is empty");
}
else
{
while(i<=rear)
{
printf("\n%d",queue[i]);
i=(i+1)%MAX;
}
}
}
***************************************************************************
*******OUTPUT
1.enqueue
2.dequeue
3.display
4.exit
1
enter value to insert 23
1.enqueue
2.dequeue
3.display
4.exit
1
enter value to insert 24
1.enqueue
2.dequeue
3.display
4.exit
3
23
24
1.enqueue
2.dequeue
3.display
4.exit
2
23 is deleted
1.enqueue
2.dequeue
3.display
4.exit
2
24 is deleted
1.enqueue
2.dequeue
3.display
4.exit
2. Write the program for double ended queue
#include<stdio.h>
#include <stdlib.h>
int deque[10]; 
int front = -1, rear = -1; 
#define MAX 10
int front,rear;
void Insert_from_Front();
void Insert_from_Rear();
void Delete_from_Front();
void Delete_from_Rear();
void Display();
void main()
{
 int ch,x;
 while(1)
 {
 printf("\nEnter the Choice");
 printf("\n1.Insert from Front\n2.Insert from Rear\n3.Delete from Front\n4.Delete From 
Rear\n5.Display\n6.exit ");
 scanf("%d",&ch);
 switch(ch)
 {
 case 1:printf("\nEnter The Val");
 scanf("%d",&x);
 Insert_from_Front( x);
 break;
 case 2:Insert_from_Rear( x);
 break; 
 case 3:Delete_from_Front();
 break; 
 case 4:Delete_from_Rear();
 break; 
 case 5:Display();
 break; 
 case 6:exit(0);
 break; 
 Default:printf("\nWrong Choice"); 
 }
 }
}
void Insert_from_Front(int x)
{
 if((front==0&&rear==MAX-1)||(front==rear+1))
 {
 printf("Queue is full");
 }
 else if(front==-1&&rear==-1)
 {
 front=0;
 rear=0;
 deque[front]=x;
 }
 else if(front==0)
 {
 front=MAX-1;
 deque[front]=x;
 }
 else
 {
 front=front-1;
 deque[front]=x;
 }
}
void Insert_from_Rear(int x)
{
 if((front==0&&rear==MAX-1)||(front==rear+1))
 {
 printf("Queue is full");
 }
 else if(front==-1&&rear==-1)
 {
 front=0;
 rear=0;
 deque[rear]=x;
 }
 else if(rear==MAX-1)
 {
 rear=0;
 deque[rear]=x;
 }
 else
 {
 rear++;
 deque [rear]=x;
 }
}
void Delete_from_Front()
{
 if(front==-1&&rear==-1)
 {
 printf("Queue is Empty");
 }
 else if(front=rear)
 {
 printf("%d is deleted",deque[front]);
 front=rear-1;
 }
 else if(rear==MAX-1)
 {
 printf("%d is deleted",deque[front]);
 front=0;
 }
 else
 {
 printf("%d is deleted",front);
 front++;
 }
}
void Delete_from_Rear()
{
 if(front==-1&&rear==-1)
 {
 printf("Queue is Empty");
 }
 else if(front=rear)
 {
 printf("%d is deleted",deque[rear]);
 front=rear-1;
 }
 else if(rear==MAX-1)
 {
 printf("%d is deleted",deque[rear]);
 rear--;
 }
 else
 {
 printf("%d is deleted",deque[rear]);
 rear=MAX-1;
 }
}
void Display()
{
 int i = front;
 if (front == -1 && rear == -1)
 {
 printf("Queue is Empty");
 }
 else
 {
 do
 {
 printf("%d\t", deque[i]);
 i = (i + 1) % MAX;
 } while (i != (rear + 1) % MAX);
 }
}
***************************************************************************
*******OUTPUT
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit
1
Enter The Val12
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit
1
Enter The Val23
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit
1
Enter The Val34
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 5
34 23 12
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 2
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 5
34 23 12 34
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 3
34 is deleted
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 4
34 is deleted
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit 5
12 34
Enter the Choice
1.Insert from Front
2.Insert from Rear
3.Delete from Front
4.Delete From Rear
5.Display
6.exit
3. Write a program to implement priority queue using array
#include <stdio.h>
#include <stdlib.h> 
#define MAX 10
void create_queue();
void insert_element(int);
void delete_element(int);
void check_priority(int);
void display_priorityqueue();
int pqueue[MAX] ;
int front, rear;
void main()
{
int n, choice; 
printf("\n enter 1 to insert element by priority ");
printf("\n enter 2 to delete element by priority");
printf("\n enter 3 to display priority queue"); 
printf("\n enter 4 to exit");
create_queue();
while (1)
{
printf("\nEnter your choice: ");
scanf("%d", &choice);
switch(choice)
{
case 1: printf("\nEnter element to insert: ");
 scanf("%d",&n);
 insert_element(n);
 break;
case 2: printf("\nEnter element to delete: ");
 scanf("%d",&n);
 delete_element(n); 
 break;
case 3: display_priorityqueue();
 break;
case 4:exit(0);
default:printf("n Please enter valid choice");
}
}
}
void create_queue()
{
front=rear=-1;
}
void insert_element(int data)
{
if (rear>= MAX-1)
{
 printf("QUEUE OVERFLOW");
 return;
}
if ((front==-1) && (rear==-1))
 {
 front++;
 rear++;
 pqueue[rear]= data;
 return;
 }
else
check_priority(data);
rear++;
}
void check_priority(int data)
{
int i,j;
for (i=0; i <=rear; i++)
{
 if(data>=pqueue[i])
 {
 for(j=rear+1;j>i;j--)
 {
 pqueue[j]=pqueue[j-1];
 }
 pqueue[i]=data;
 return;
 }
}
pqueue[i]=data;
}
void delete_element(int data)
{
 int i;
 if((front==-1)&&(rear==-1))
 {
 printf("\nEmpty Queue");
 return;
 }
 for(i=0;i<=rear;i++)
 {
 if(data==pqueue[i])
 {
 for(i=0;i<rear;i++)
 {
 pqueue[i]=pqueue[i+1];
 }
 pqueue[i]=data;
 rear--;
 if(rear==-1)
 front=-1;
 return;
 }
 }
 printf("\n%d element not found in queue ",data); 
}
void display_priorityqueue()
{
 if((front==-1)&&(rear==-1))
 {
 printf("\nEmpty Queue");
 return;
 }
 for(front=0;front<=rear;front++)
 {
 printf("%d\n",pqueue[front]);
 }
 front=0;
}
OUTPUT
enter 1 to insert element by priority
enter 2 to delete element by priority
enter 3 to display priority queue
enter 4 to exit
Enter your choice: 1
Enter element to insert: 23
Enter your choice: 1
Enter element to insert: 34
Enter your choice: 1
Enter element to insert: 12
Enter your choice: 1
Enter element to insert: 16
Enter your choice: 3
34
23
16
12
Enter your choice: 2
Enter element to delete: 34
Enter your choice: 3
23
16
12
Enter your choice: 2
Enter element to delete: 16
Enter your choice: 3
16
12
Enter your choice:
4. Write a c program to covert a given infix expression to postfix expression from 
using stack
#include<stdio.h>
#include<stdlib.h> 
#include<ctype.h> 
#include<string.h>
#define SIZE 100
char stack[SIZE];
int top = -1;
void push(char item)
{
if(top >= SIZE-1)
{
printf("\nStack Overflow.");
}
else
{
top = top+1;
stack[top] = item;
}
}
char pop()
{
char item ;
if(top <0)
{
printf("stack under flow: invalid infix expression");
getchar();
exit(1);
}
else
{
item = stack[top];
top = top-1;
return(item);
}
}
int is_operator(char symbol)
{
if(symbol == '^' || symbol == '*' || symbol == '/' || symbol == '+' || symbol =='-')
{
return 1;
}
else
{
return 0;
}
}
int precedence(char symbol)
{
if(symbol == '^')
{
return(3);
}
else if(symbol == '*' || symbol == '/')
{
return(2);
}
else if(symbol == '+' || symbol == '-') 
{
return(1);
}
else
{
return(0);
}
}
void InfixToPostfix(char infix_exp[], char postfix_exp[])
{
int i, j;
char item;
char x;
push('('); 
strcat(infix_exp,")"); 
i=0;
j=0;
item=infix_exp[i]; 
while(item != '\0') 
{
if(item == '(')
{
push(item);
}
else if( isdigit(item) || isalpha(item))
{
postfix_exp[j] = item; 
j++;
}
else if(is_operator(item) == 1) 
{
x=pop();
while(is_operator(x) == 1 && precedence(x)>= precedence(item))
{
postfix_exp[j] = x; 
j++;
x = pop(); 
}
push(x);
push(item); 
 } 
else if(item == ')') 
{
x = pop(); 
while(x != '(') 
{
postfix_exp[j] = x;
j++;
x = pop();
}
}
else
{ 
printf("\nInvalid infix Expression.\n"); 
getchar();
exit(1);
}
i++;
item = infix_exp[i]; 
} 
if(top>0)
{
printf("\nInvalid infix Expression.\n"); 
getchar();
exit(1);
}
if(top>0)
{
printf("\nInvalid infix Expression.\n"); 
getchar();
exit(1);
}
postfix_exp[j] = '\0'; 
}
int main()
{
char infix[SIZE], postfix[SIZE]; 
printf("\nEnter Infix expression : ");
gets(infix);
InfixToPostfix(infix,postfix); 
printf("Postfix Expression: ");
puts(postfix); 
return 0;
}
OUTPUT
Enter Infix expression : (a+b-(c*d*f)/g-h)
Postfix Expression: ab+cd*f*g/-h-
5. Write a program to evaluate a given postfix expression using stack
#include<stdio.h> 
#include<conio.h> 
#include<string.h> 
#defne MAX 50 
int stack[MAX]; 
char post[MAX]; 
int top=-1; 
void pushstack(int tmp); 
void evaluate(char c); 
void main()
{
 int i,l;
 printf("Insert a postfix notation :: ");
 scanf("%s",post); 
 l=strlen(post); 
 for(i=0;i<l;i++)
 {
 if(post[i]>='0' && post[i]<='9')
 {
 pushstack(i); 
 }
 if(post[i]=='+' || post[i]=='-' || post[i]=='*' || post[i]=='/' || post[i]=='^') 
 {
 evaluate(post[i]); 
 }
 } 
 printf("\n\nResult :: %d",stack[top]);
 getch();
}
void pushstack(int tmp) 
{
 top++; 
 stack[top]=(int)(post[tmp]-48); 
}
void evaluate(char c) 
{
 int a,b,ans; 
 a=stack[top]; 
 stack[top]='\0'; 
 top--; 
 b=stack[top]; 
 stack[top]='\0'; 
 top--; 
 switch(c) 
 {
 case '+': 
 ans=b+a;
 break;
 case '-': 
 ans=b-a;
 break;
 case '*': 
 ans=b*a;
 break;
 case '/': 
 ans=b/a;
 break;
 case '^': 
 ans=b^a;
 break;
 default:
 ans=0; 
 }
 top++; 
 stack[top]=ans; 
}
***************************************************************************
*******OUTPUT
Insert a postfix notation :: 5 4 *6 7+-
Result :: 7
6. Write a C-program of implementing stack using two queues:
#include <stdio.h>
#include<conio.h>
#define N 20
int queue1[N],queue2[N];
int f1= -1, r1= -1;
int f2= -1, r2= -1;
int count=0;
void enqueue1(int x);
int dequeue1();
void enqueue2(int x);
int dequeue2();
void push(int x);
int pop();
void display();
void main()
{ 
int ch, num;
while (ch != 4)
{ 
 printf("\n1.Push Item\n2.Pop Item\n3.Display Item\n4.Exit\n");
 printf("\nEnter your choice :");
 scanf("%d", &ch);
 switch (ch)
 {
 case 1: printf("Entre item to be inserted : ");
 scanf("%d", &num);
 push(num); 
 break;
 case 2: printf("Item deleted : %d",pop()); 
 break;
 case 3: display(); 
 break;
 case 4: exit(0);
 break; 
 default:printf("\nInvalide Choice !!!\n"); 
 }
}
}
void enqueue1(int x)
{
 if(r1==N-1)
 {
 printf("Overflow");
 }
 else
 {
 if(f1== -1)
 {
f1=0;
 }
 r1=r1+1;
 queue1[r1]=x;
 }
}
int dequeue1()
{
 int temp;
 if(f1== -1 || f1 > r1)
 {
 printf("underflow");
 }
 else
 {
 temp = queue1[f1];
 f1++;
 }
 return(temp);
}
void enqueue2(int x)
{
 if(r2==N-1)
 {
 printf("Overflow");
 }
 else
 {
 if(f2== -1)
 {
 f2=0;
 }
 r2=r2+1;
 queue2[r2]=x;
}
}
int dequeue2()
{
 int temp;
 if(f2== -1 || f2 > r2)
 {
 printf("Underflow");
 }
 else
 {
 temp = queue2[f2];
 f2++;
 }
 return(temp);
}
void push(int x)
{
int i;
enqueue1(x);
for (i = 0; i < count ; i++)
{
 enqueue1(dequeue2());
}
count++;
for(i=0; i<count;i++)
{
 enqueue2(dequeue1());
}
}
int pop()
{
count--;
return dequeue2();
}
void display()
{
 int i;
 printf("\nElements in Stack : ");
 for (i = f2; i <=r2 ; i++)
{
 printf("%d ", queue2[i]);
}
printf("\n");
}
***************************************************************************
*******OUTPUT
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :1
Entre item to be inserted : 12
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :1
Entre item to be inserted : 34
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :1
Entre item to be inserted : 45
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :1
Entre item to be inserted : 43
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :3
Elements in Stack : 43 45 34 12
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :2
Item deleted : 43
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :2
Item deleted : 45
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :2
Item deleted : 34
1.Push Item
2.Pop Item
3.Display Item
4.Exit
Enter your choice :2
Item deleted : 12
1.Push Item
2.Pop Item
3.Display Item
4.Exit
7. Write a program to implement queue using two stack
#include <stdio.h>
#include <stdlib.h>
struct node
{
 int data;
 struct node *next;
};
void push(struct node** top, int data);
int pop(struct node** top);
struct queue
{
 struct node *stack1;
 struct node *stack2;
};
void enqueue(struct queue *q, int x)
{
 push(&q->stack1, x);
}
void dequeue(struct queue *q)
{
 int x;
 if (q->stack1 == NULL && q->stack2 == NULL) {
 printf("queue is empty");
 return;
 }
 if (q->stack2 == NULL) {
 while (q->stack1 != NULL) {
 x = pop(&q->stack1);
 push(&q->stack2, x);
 }
 }
 x = pop(&q->stack2);
 printf("%d\n", x);
}
void push(struct node** top, int data)
{
 struct node* newnode = (struct node*) malloc(sizeof(struct node));
 if (newnode == NULL) {
 printf("Stack overflow \n");
 return;
 }
 newnode->data = data;
 newnode->next = (*top);
 (*top) = newnode;
}
int pop(struct node** top)
{
 int buff;
 struct node *t;
 if (*top == NULL) {
 printf("Stack underflow \n");
 return;
 }
 else {
 t = *top;
 buff = t->data;
 *top = t->next;
 free(t);
 return buff;
 }
}
void display(struct node *top1,struct node *top2)
{
 while (top1 != NULL) {
 printf("%d\n", top1->data);
 top1 = top1->next;
 }
 while (top2 != NULL) {
 printf("%d\n", top2->data);
 top2 = top2->next;
 }
}
int main()
{
 struct queue *q = (struct queue*)malloc(sizeof(struct queue));
 int f = 0, a;
 char ch = 'y';
 q->stack1 = NULL;
 q->stack2 = NULL;
 while (ch == 'y'||ch == 'Y') {
 printf("enter ur choice\n1.add to queue\n2.remove from queue\n3.display\n4.exit\n");
 scanf("%d", &f);
 switch(f) {
 case 1 : printf("enter the element to be added to queue\n");
 scanf("%d", &a);
 enqueue(q, a);
 break;
 case 2 : dequeue(q);
 break;
 case 3 : display(q->stack1, q->stack2);
 break;
 case 4 : exit(1);
 break;
 default : printf("invalid\n");
 break;
 }
 }
}
OUTPUT
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
1
enter the element to be added to queue
12
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
1
enter the element to be added to queue
23
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
1
enter the element to be added to queue
13
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
1
enter the element to be added to queue
67
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
3
67
13
23
12
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
2
12
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
2
23
enter ur choice
1.add to queue
2.remove from queue
3.display
4.exit
2
13
Write programme to implement the following data structure.
1. Singly link list 
#include<stdio.h>
#include<stdlib.h>
struct node{
int data;
struct node*next;
};
struct node*head;
struct node*ptr;
struct node*temp;
void insert_begin(int val);
void insert_end(int val);
void insert_pos(int val);
void delete_begin();
void delete_end();
void delete_pos();
void display();
void exit();
int main()
{
int ch,val;
while(1)
{
 printf("\n1.insert at begin \n2.insert at end \n3.insert at pos \n4.delete at begin 
\n5.delete at end \n6.delete at pos \n7.display \n8.exit");
 printf("\nenter your choice");
 scanf("%d",&ch);
 switch(ch)
 {
 case 1: printf("enter the value");
 scanf("%d",&val);
 insert_begin(val);
 break;
 case 2: insert_end(val); 
 break;
 case 3: insert_pos(val); 
 break;
 case 4: delete_begin();
 break;
 case 5:delete_end();
 break;
 case 6:delete_pos();
 break;
 case 7:display();
 break;
 case 8:exit(0);
 break;
 defazult:printf("enter wrong choice");
 break;
 
 }
 
 }
}
void insert_begin(int val)
{
 ptr = (struct node *)malloc(sizeof(struct node));
 if (ptr == NULL)
 {
 printf("memory is not allocated");
 }
 else
 {
 ptr->data = val;
 ptr->next = head; // Link the new node to the current head
 head = ptr; // Make the new node the head of the list
 }
}
void insert_end(int val)
{
 ptr = (struct node *)malloc(sizeof(struct node));
 if (ptr == NULL)
 {
 printf("memory is not allocated");
 }
 else
 {
 ptr->data = val;
 ptr->next = NULL; 
 if (head == NULL)
 {
 head = ptr; 
 }
 else
 {
 temp = head;
 while (temp->next != NULL)
 {
 temp = temp->next;
 }
 temp->next = ptr; 
 }
 }
}
void insert_pos(int val)
{
 int loc;
 ptr = (struct node *)malloc(sizeof(struct node));
 if (ptr == NULL)
 {
 printf("memory is not allocated");
 }
 else
 {
 printf("enter location where you want to insert");
 scanf("%d", &loc);
 if (loc == 1)
 {
 // Insert at the beginning
 ptr->data = val;
 ptr->next = head;
 head = ptr;
 }
 else
 {
 temp = head;
 for (int i = 0; i < loc - 2; i++) // Traverse to the node before the specified location
 {
 temp = temp->next;
 if (temp == NULL)
 {
 printf("cannot insert");
 free(ptr); // Free the allocated memory before returning
 return;
 }
 }
 ptr->data = val;
 ptr->next = temp->next;
 temp->next = ptr;
 }
 }
}
void delete_begin()
{
temp=head;
if(head==NULL)
{
printf("list is empty");
}
else
{
 head=temp->next;
 temp->next=NULL;
 printf("%d is deleted",temp->data);
 free(temp);
}
}
 void delete_end()
{
 struct node *temp1;
 struct node *ptr1;
 temp = head;
 if (head == NULL)
 {
 printf("list is empty");
 }
 else if (head->next == NULL)
 {
 printf("%d is deleted", temp->data);
 free(head);
 head = NULL; 
 }
 else
 {
 while (temp->next != NULL)
 {
 ptr1 = temp;
 temp = temp->next;
 }
 ptr1->next = NULL;
 printf("%d is deleted", temp->data);
 free(temp);
 }
}
 void delete_pos()
{
struct node*temp1;
temp=head;
int loc;
if(head==NULL)
{
printf("cannot delete");
}
else
{
printf("enter location");
scanf("%d",&loc);
for(int i=0;i<loc-1;i++)
{
temp1=temp;
temp=temp->next;
if(temp==NULL)
{
printf("cannot delete");
}
}
temp1->next=temp->next;
temp->next=NULL;
printf("%d is deleted",temp->data);
free(temp);
}
}
 void display()
 {
 temp=head;
 if(head==NULL)
 {
 printf("list is empty");
 
 }
 else
 {
 do
 {
 printf("\t %d ",temp->data);
temp=temp->next; 
 }while(temp!=NULL);
 }
 }
*********************************************************************
*************OUTPUT
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the value56
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the value23
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the value45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 45 23 56
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice2
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 45 23 56 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice3
enter location where you want to insert2
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 45 45 23 56 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice4
45 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 45 23 56 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice5
45 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice5
56 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice6
enter location2
23 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice
Doubly linked list
#include<stdio.h>
#include<stdlib.h>
struct node{
int data;
struct node*next;
struct node*prev;
};
struct node*head;
struct node*ptr;
struct node*temp;
struct node*temp1;
void insert_begin(int val);
void insert_end(int val);
void insert_pos(int val);
void delete_begin();
void delete_end();
void delete_pos();
void display();
int main()
{
int ch,val;
while(1)
{
 printf("\n1.insert at begin \n2.insert at end \n3.insert at pos \n4.delete at begin 
\n5.delete at end \n6.delete at pos \n7.display \n8.exit");
 printf("\nenter your choice");
 scanf("%d",&ch);
 switch(ch)
 {
 case 1: insert_begin(val);
 break;
 case 2: insert_end(val); 
 break;
 case 3: insert_pos(val); 
 break;
 case 4: delete_begin();
 break;
 case 5:delete_end();
 break;
 case 6:delete_pos();
 break;
 case 7:display();
 break;
 case 8:exit(0);
 break;
 default:printf("enter wrong choice");
 break;
 
 }
 
 }
}
void insert_begin(int val)
{
 printf("\n enter the number");
ptr=(struct node*)malloc(sizeof(struct node));
if(ptr==NULL)
{
printf("memory is not allocated");
}
else
{
 scanf("%d",&ptr->data);
 if(head==NULL)
{
 ptr->next=NULL;
ptr->prev=NULL;
head=ptr;
}
else
{
 ptr->next=head;
 ptr->prev=NULL;
 head->prev=ptr;
head=ptr;
}
 }
}
void insert_end(int val)
{
 printf("\n enter the no.");
ptr=(struct node*)malloc(sizeof(struct node));
if(ptr==NULL)
{
printf("memory is not allocated");
}
else
{ 
 scanf("%d",&ptr->data);
 if(head==NULL)
 {
 ptr->next=NULL;
ptr->prev=NULL;
head=ptr;
 }
 else
 {
temp=head;
while(temp->next!=NULL)
{
temp=temp->next;
}
ptr->next=NULL;
temp->next=ptr; 
ptr->prev=temp;
 }
 }
 printf("node is inserted");
}
void insert_pos(int val)
{
int i,loc;
printf("enter location where you want to insert");
scanf("%d",&loc);
temp=head;
for( i=0;i<loc-1;i++)
{
temp=temp->next;
if(temp==NULL)
{
 printf("cannot insert");
 return;
}
}
ptr=(struct node*)malloc(sizeof(struct node));
if(ptr==NULL)
{
printf("memory is not allocated");
}
else
{
printf("\n enter value:");
scanf("%d",&ptr->data);
 ptr->next=temp->next;
 ptr->next->prev=ptr;
temp->next=ptr;
ptr->prev=temp;
}
printf("node is inserted");
}
void delete_begin()
{
 if(head==NULL) 
 {
 printf("can't delete");
 }
 else if(head->next==NULL)
 {
 printf("\n%d is deleted",head->data);
 free(head);
 }
 else
 {
 temp=head;
 printf("\n%d is deleted",temp->data);
 head=head->next;
 temp->next=NULL;
 head->prev=NULL;
 free(temp);
 }
}
void delete_end()
{
 if(head==NULL)
 {
 printf("linked list is empty");
 }
 else if(head->next==NULL)
 {
 printf("\n%d id deleted",head->data);
 free(head);
 }
 else
 {
 temp=head;
 while(temp->next!=NULL)
 {
 temp=temp->next;
 }
 temp->prev->next=NULL;
 temp->prev=NULL;
 printf("\n %d is deleted",temp->data);
 free(temp);
 }
}
void delete_pos()
{
 int i,loc;
 if(head==NULL)
 {
 printf("linked list is empty");
 }
 else
 {
 temp=head;
 printf("\n enter location");
 scanf("%d",&loc);
 for(i=0;i<loc;i++)
 {
 temp=temp->next;
 if(temp==NULL)
 {
 printf("can't delete");
 }
 }
 temp1=temp->next;
 temp->next=temp1->next;
 temp1->next->prev=temp;
 temp1->next=NULL;
 temp1->prev=NULL;
 printf("\n%d is deleted",temp1->data);
 free(temp1);
 }
}
void display()
{
 temp = head; // Assuming 'temp' is a global variable or declared in the correct scope
 if (head == NULL)
 {
 printf("list is empty");
 }
 else
 {
 while (temp != NULL)
 {
 printf("\t %d ", temp->data);
 temp = temp->next;
 }
 }
}
Output
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the number34
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the number98
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice1
enter the number78
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 78 98 34
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice2
enter the no.45
node is inserted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 78 98 34 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice3
enter location where you want to insert2
enter value:22
node is inserted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice7
 78 98 22 34 45
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice4
78 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice5
45 is deleted
1.insert at begin
2.insert at end
3.insert at pos
4.delete at begin
5.delete at end
6.delete at pos
7.display
8.exit
enter your choice6
enter location3
can't delete
Write the programme to implement the circular singly linked list.
#include<stdio.h>
#include<stdlib.h>
struct node
{
 int data;
 struct node *next;
};
struct node *head,*ptr,*temp,*head,*temp1;
void insert_begin();
void insert_last();
void delete_begin();
void delete_last();
void search();
void display();
void main()
{
 int ch;
 while(1)
 {
 printf("\n1. insert at begin\n2.insert at last\n3.delete at begin\n4.delete at 
last\n5.search\n6.display\n7.exit\n");
 printf("enter your choice\n");
 scanf("%d",&ch);
 switch(ch)
 {
 case 1:insert_begin();
 break;
 case 2:insert_last();
 break;
 case 3:delete_begin();
 break;
 case 4:delete_last();
 break;
 case 5:search();
 break;
 case 6:display();
 break;
 case 7:exit(0);
 break; 
 default:printf("invalid choice");
 }
 }
}
void insert_begin()
{
 ptr=(struct node*)malloc(sizeof(struct node));
 if(ptr==NULL)
 {
 printf("memory is not allocated\n");
 }
 else
 {
 printf("enter the value\n");
 scanf("%d",&ptr->data);
 if(head==NULL)
 {
 head=ptr;
 ptr->next=head;
 }
 else
 {
 temp=head;
 while(temp->next!=head)
 {
 temp=temp->next;
 }
 ptr->next=head;
 temp->next=ptr;
 head=ptr; 
 }
 }
 printf("node is inserted\n");
}
void insert_last()
{
 ptr = (struct node*)malloc(sizeof(struct node));
 if(ptr == NULL)
 {
 printf("memory is not allocated");
 return;
 }
 printf("enter the value: ");
 scanf("%d", &ptr->data);
 if(head == NULL)
 {
 head = ptr;
 ptr->next = head;
 }
 else
 {
 temp = head;
 while(temp->next != head)
 {
 temp = temp->next;
 }
 temp->next = ptr;
 ptr->next = head;
 }
 printf("node is inserted\n");
}
void delete_begin()
{
 if(head == NULL)
{
 printf("\nUNDERFLOW");
}
else if(head->next == head)
{
 head = NULL;
 free(head);
 printf("\nnode deleted\n");
}
else
{
 ptr = head;
 while(ptr -> next != head)
 ptr = ptr -> next;
 ptr->next = head->next;
 free(head);
 head = ptr->next;
 printf("\n node deleted\n");
} 
}
void delete_last()
{
 if (head==NULL)
 {
 printf("linkedlist is empty\n");
 }
 else if (head->next==head)
 {
 printf("%d is deleted",head->data);
 free(head);
 }
 else
 {
 temp=head;
 while(temp->next!=head)
 {
 temp1=temp;
 temp=temp->next;
 }
 temp1->next=head;
 temp->next=NULL;
 printf("%d is deleted",temp->data);
 free(temp);
 }
 printf("\n node is deleted");
}
void search()
{
 int val,i=0,flag=0;
 temp = head;
if(head == NULL)
{
 printf("\nEmpty List\n");
}
else
{
 printf("\nEnter item which you want to search?\n");
 scanf("%d",&val);
 while(temp!=head)
 {
 if(temp->data == val)
 {
 printf("item found at location %d",val);
 }
 else
 {
 flag=1;
 }
 i++;
 temp=temp->next;
 }
 if(flag==1)
 {
 printf("value is not found");
 }
}
}
void display()
{
 ptr = head;
 if (head == NULL)
 {
 printf("\nnothing to print");
 }
 else
 {
 printf("\n printing values ... \n");
 do
 {
 printf("\n%d", ptr->data);
 ptr = ptr->next;
 } while (ptr != head);
 }
}
OUTPUT
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
1
enter the value
24
node is inserted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
1
enter the value
46
node is inserted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
1
enter the value
79
node is inserted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
6
printing values ...
79
46
24
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
2
enter the value: 4
node is inserted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
2
enter the value: 64
node is inserted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
6
printing values ...
79
46
24
4
64
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
3
node deleted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
6
printing values ...
46
24
4
64
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
4
64 is deleted
node is deleted
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
6
printing values ...
46
24
4
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
5
Enter item which you want to search?
2
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
6
printing values ...
46
24
4
1. insert at begin
2.insert at last
3.delete at begin
4.delete at last
5.search
6.display
7.exit
enter your choice
Write programme to implement to binary tree
#include<stdio.h>
#include<stdlib.h>
struct node
{
 int data;
 struct node *left;
 struct node *right;
};
struct node *root = NULL;
// Function prototype
struct node *create();
void pre_order_traversal(struct node* root) {
 if(root != NULL) {
 printf("%d ", root->data);
 pre_order_traversal(root->left);
 pre_order_traversal(root->right);
 }
}
void inorder_traversal(struct node* root) {
 if(root != NULL) {
 inorder_traversal(root->left);
 printf("%d ", root->data);
 inorder_traversal(root->right);
 }
}
void post_order_traversal(struct node* root) {
 if(root != NULL) {
 post_order_traversal(root->left);
 post_order_traversal(root->right);
 printf("%d ", root->data);
 }
}
struct node *create() {
 struct node *temp;
 int data, choice;
 temp = (struct node *)malloc(sizeof(struct node));
 
 printf("Press 0 to exit");
 printf("\nPress 1 for a new node");
 printf("\nEnter your choice: ");
 scanf("%d", &choice);
 if(choice == 0) {
 return NULL;
 } else {
 printf("Enter the data: ");
 scanf("%d", &data);
 temp->data = data;
 printf("Enter the left child of %d\n", data);
 temp->left = create();
 printf("Enter the right child of %d\n", data);
 temp->right = create();
 return temp;
 }
OUTPUT
1. Create
2. Inorder
3. Preorder
4. Postorder
5. Exit
Enter your choice: 1
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 24
Enter the left child of 24
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 12
Enter the left child of 12
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 78
Enter the left child of 78
Press 0 to exit
Press 1 for a new node
Enter your choice: 0
Enter the right child of 78
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 45
Enter the left child of 45
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 90
Enter the left child of 90
Press 0 to exit
Press 1 for a new node
Enter your choice: 1
Enter the data: 89
Enter the left child of 89
Press 0 to exit
Press 1 for a new node
Enter your choice: 0
Enter the right child of 89
Press 0 to exit
Press 1 for a new node
Enter your choice: 0
Enter the right child of 90
Press 0 to exit
Press 1 for a new node
Enter your choice: 2
Enter the data: 12
Enter the left child of 12
4 .Write programme to implement Binary search tree.
#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
struct node
{
 int data;
 struct node *left, *right;
};
struct node *createtree(struct node *root, int data);
void search(struct node *root);
void findmax(struct node *root);
struct node *delet(struct node *root, int data);
struct node *findmin(struct node *root);
void preorder(struct node *root);
void inorder(struct node *root);
void postorder(struct node *root);
struct node *root = NULL;
void main()
{
 struct node *temp;
 int data, ch, i, n;
 while(1)
 {
 printf("\n1.Insertion in Binary Search Tree");
 printf("\n2.Search Element in Binary Search Tree");
 printf("\n3.Delete Element in Binary Search Tree");
 printf("\n4.Inorder\n5.Preorder\n6.Postorder\n7.Find Min\n8.Find Max\n9.Exit");
 printf("\nEnter your choice: ");
 scanf("%d",&ch);
 switch (ch)
 {
 case 1: printf("\nEnter how many nodes u want to insert: " );
 scanf("%d", &n);
 printf("\n enter values: ");
 for(i=0; i<n; i++)
 {
 scanf("%d", &data);
 root=createtree(root, data);
 }
 break;
 case 2: search(root);
 break;
 case 3: printf("\nEnter the element to delete: ");
 scanf("%d", &data);
 root=delet(root, data);
 break;
 case 4: printf("\nInorder Traversal: \n");
 inorder(root);
 break;
 case 5: printf("\nPreorder Traversal: \n");
 preorder(root);
 break;
 case 6: printf("\nPostorder Traversal: \n");
 postorder(root);
 break;
 case 7: temp=findmin(root);
 printf("\n %d is minimum no in BST",temp->data);
 break;
 case 8: findmax(root);
 break;
 case 9: exit(0);
 default: printf("WRONG CHOICE");
 break;
 }
 }
}
struct node *createtree(struct node *root, int data)
{
 if (root == NULL)
 {
 struct node *temp;
 temp= (struct node*)malloc(sizeof(struct node));
 temp->data = data;
 temp->left = NULL;
 temp->right = NULL;
 return(temp);
 }
 if (data < (root->data))
 {
 root->left = createtree(root->left, data);
 }
 else if (data > root->data)
 {
 root->right = createtree(root->right, data);
 }
 return root;
}
void preorder(struct node *root)
{
 if(root != NULL)
 {
 printf("%d ",root->data);
 preorder(root->left);
 preorder(root->right);
 }
}
void inorder(struct node *root)
{
 if(root != NULL)
 {
 inorder(root->left);
 printf("%d ",root->data);
 inorder(root->right);
 }
}
void postorder(struct node *root)
{
 if(root != NULL)
 {
 postorder(root->left);
 postorder(root->right);
 printf("%d ", root->data);
 }
}
struct node *delet(struct node *root, int data)
{
 struct node *temp;
 if(root == NULL)
 {
 printf("\nElement not found");
 }
 else if(data < root->data)
 {
 root->left = delet(root->left, data);
 }
 else if(data > root->data)
 {
 root->right = delet(root->right, data);
 }
 else
 {
 /* Now We can delete this node and replace with either minimum element in the right sub 
tree or maximum element in the left subtree */
 if(root->right && root->left)
 { /* Here we will replace with minimum element in the right sub tree */
 temp = findmin(root->right);
 root->data = temp->data;
 /* As we replaced it with some other node, we have to delete that node */
 root->right = delet(root->right,temp->data);
 }
 else
 {
 /* If there is only one or zero children then we can directly remove it from the tree and 
connect its parent to its child */
 temp = root;
 if(root->left == NULL)
 root = root->right;
 else if(root->right == NULL)
 root = root->left;
 free(temp); /* temp is longer required */
 }
 }
 return root;
}
struct node *findmin(struct node *root)
{
 struct node *temp;
 temp = root;
 if(temp==NULL)
 {
 return NULL;
 }
 if(temp->left)
 return findmin(temp->left);
 else
 return temp;
}
void findmax(struct node *root)
{
 if(root==NULL)
 {
 return NULL;
 }
 if(root->right)
 findmax(root->right);
 else
 printf("\n %d is maximum no in BST",root->data);
}
void search(struct node *root)
{
 int data;
 if(root == NULL)
 {
 printf("\nBST is empty.");
 return;
 }
 printf("\nEnter Element to be searched: ");
 scanf("%d", &data);
 while(root != NULL)
 {
 if (root->data == data)
 {
 printf("\nKey element is present in BST");
 return;
 }
 if (data < root->data)
 root = root->left;
 else
 root = root->right;
 }
 printf("\nKey element is not found in the BST");
}
OUTPUT
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 1
Enter how many nodes u want to insert: 2
enter values: 12
23
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 1
Enter how many nodes u want to insert: 2
enter values: 78 45
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 3
Enter the element to delete: 78
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 4
Inorder Traversal:
12 23 45
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 5
Preorder Traversal:
12 23 45
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 6
Postorder Traversal:
45 23 12
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 7
12 is minimum no in BST
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Enter your choice: 8
45 is maximum no in BST
1.Insertion in Binary Search Tree
2.Search Element in Binary Search Tree
3.Delete Element in Binary Search Tree
4.Inorder
5.Preorder
6.Postorder
7.Find Min
8.Find Max
9.Exit
Write programme to implement Hash table.
#include<stdio.h>
#include<conio.h>
#define size 10
int arr[size];
void init();
void insert(int value);
void del(int value);
void print();
int main()
{
 int ch =0,temp;
 init();
 while (ch!=4)
 {
 printf("\n1.Insert\n2.Delete\n3.Print hash table\n4.Exit\nEntre your choice: ");
 scanf("%d",&ch);
 switch(ch)
 {
 case 1 : printf("Entre element to be inserted : ");
 scanf("%d",&temp);
 insert(temp);
 break;
 case 2 : printf("Entre element to be deleted : ");
 scanf("%d",&temp);
 del(temp);
 break;
 case 3 : print();
 break;
 case 4 : exit(0);
 break;
 default : printf("wrong input !!!");
 }
 }
 return 0;
}
void init()
{
 int i;
 for(i = 0; i < size; i++)
 arr[i] = -1;
}
void insert(int value)
{
 int flag=1;
 int key = value % size;
 if(arr[key] == -1)
 {
 arr[key] = value;
 printf("%d inserted with key %d !\n", value,key);
 }
 else
 {
 printf("Collision : key %d has element %d already!\n",key,arr[key]);
 while(flag)
 {
 while(arr[key]!=-1)
 {
 key++;
 }
 if(key != size-1)
 {
 //if(arr[key] == -1)
 //{
 arr[key] = value;
 printf("%d inserted with key %d !\n", value,key);
 flag=0;
 }
 else
 printf("\n Unable to insert");
 }
 }
}
//delete item from table
void del(int value)
{
 /*int key = value % size;
 if(arr[key] == value)
 arr[key] = -1;
 else
 printf("%d not present in the hash table\n",value);*/
 int i;
 for(i =0; i<size-1; i++)
 {
 if(arr[i] == value)
 {
 arr[i] = -1;
 printf("\n %d is deletd",value);
 }
 }
}
//hash table print method
void print()
{
 int i;
 printf("\nVALUE\t---\tKEY");
 printf("\n===================\n");
 for(i = 0; i < size; i++)
 {
 if(arr[i]!=-1)
 {
 printf("%d\t---\t%d\n",arr[i],i);
 }
 }
}
OUTPUT
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 1
Entre element to be inserted : 45
45 inserted with key 5 !
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 1
Entre element to be inserted : 67
67 inserted with key 7 !
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 1
Entre element to be inserted : 90
90 inserted with key 0 !
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 1
Entre element to be inserted : 34
34 inserted with key 4 !
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 3
VALUE --- KEY
===================
90 --- 0
34 --- 4
45 --- 5
67 --- 7
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 2
Entre element to be deleted : 34
34 is deletd
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice: 3
VALUE --- KEY
===================
90 --- 0
45 --- 5
67 --- 7
1.Insert
2.Delete
3.Print hash table
4.Exit
Entre your choice:
Write a program to implement selection sort
#include<stdio.h>
#include<stdlib.h>
void selection_sort(int a[],int n);
void display(int a[], int n);
int a[10], n;
int main()
{
 int i,ch;
 printf("\n enter how many elements u want to insert: ");
 scanf("%d",&n);
 printf("\n enter the elements: ");
 for(i=0;i<n;i++)
 {
 scanf("%d",&a[i]);
 }
 while(1)
 {
 printf("\n1. Sort array");
 printf("\n2. display sorted array");
 printf("\n3. exit");
 printf("\n Enter your choice: ");
 scanf("%d", &ch);
 switch(ch)
 {
case 1: selection_sort(a,n);
printf("\n array is sorted: ");
break;
case 2: display(a,n);
break;
case 3: exit(0);
default: printf("\n wrong choice: ");
 }
 }
 // getch();
}
void selection_sort(int a[], int n)
{
 int i,j,small, temp;
 for(i=0;i<n-1;i++)
 {
 small=i;
 for(j=i+1;j<n;j++)
 {
if(a[j]<a[small])
{
 small=j;
}
 }
 temp=a[small];
 a[small]=a[i];
 a[i]=temp;
 }
}
void display(int a[], int n)
{
 int i;
 printf("\n sorted array is: ");
 for(i=0;i<n;i++)
 {
 printf("\n %d",a[i]);
 }
}
OUTPUT
enter how many elements u want to insert: 5
enter the elements: 23 45 67 78 12 2
1. Sort array
2. display sorted array
3. exit
Enter your choice:
sorted array is:
23
45
67
78
12
1. Sort array
2. display sorted array
3. exit
Enter your choice: 1
array is sorted:
1. Sort array
2. display sorted array
3. exit
Enter your choice: 2
sorted array is:
12
23
45
67
78
1. Sort array
2. display sorted array
3. exit
Enter your choice:
Write a program to implement insertion sort
#include <stdio.h>
void insertionsort(int a[], int n) 
{ 
 int i, j, temp; 
 for (i = 1; i < n; i++)
 { 
 temp = a[i]; 
 j = i - 1; 
 
 while(j>=0 && temp <= a[j]) 
 { 
 a[j+1] = a[j]; 
 j = j-1; 
 } 
 a[j+1] = temp; 
 } 
} 
int main()
{
 int a[20],n,i;
 printf("\n how many elements you want to insert: ");
 scanf("%d",&n);
 printf("\n enter values: ");
 for(i=0;i<n;i++)
 {
 scanf("%d",&a[i]);
 }
 insertionsort(a,n);
 printf("\n sorted array is : ");
 for(i=0; i<n; i++)
 {
 printf("\t %d ",a[i]);
 }
 return 0;
}
OUTPUT
how many elements you want to insert: 5
enter values: 12 34 56 23 1
sorted array is : 1 12 23 34 56
write a program to implement merge sort
#include<stdio.h>
void mergesort(int a[], int lb, int ub);
void merge(int a[], int lb, int mid, int ub);
void main()
{
 int i,n,a[20];
 printf("\n Enter how many elements u want to enter: ");
 scanf("%d",&n);
 printf("\n Enter the %d elemets in array: ",n);
 for(i=0;i<n;i++)
 {
 scanf("%d", &a[i]);
 }
 mergesort(a,0,n-1);
 printf("\n sorted array is: ");
 for(i=0;i<n;i++)
 {
 printf(" %d ",a[i]);
 }
 getch();
}
void mergesort(int a[], int lb, int ub)
{
 int mid;
 if(lb<ub)
 {
 mid=(lb+ub)/2;
 mergesort(a,lb,mid);
 mergesort(a, mid+1,ub);
 merge(a,lb,mid,ub);
 }
}
void merge(int a[], int lb, int mid, int ub)
{
 int i,j,k;
 int b[20];
 i=lb;
 j=mid+1;
 k=lb;
 while(i<=mid && j<=ub)
 {
 if(a[i]<=a[j])
 {
b[k]=a[i];
k++;
i++;
 }
 else
 {
b[k]=a[j];
j++;
k++;
 }
 }
 while(i<=mid)
 {
 b[k]=a[i];
 i++;
 k++;
 }
 while(j<=ub)
 {
 b[k]=a[j];
 k++;
 j++;
 }
 for(k=0;k<=ub;k++)
 {
 a[k]=b[k];
 }
}
OUTPUT
Enter how many elements u want to enter: 5
Enter the 5 elemets in array: 12 34 76 9 6
sorted array is: 6 9 12 34 76
Write a program to implement quick sort
#include<stdio.h>
#include<stdlib.h>
void quicksort(int a[], int first, int last);
void main()
{
 int i,n,a[20];
 printf("\n Enter how many elements u want to enter: ");
 scanf("%d",&n);
 printf("\n Enter the %d elemets in array: ",n);
 for(i=0;i<n;i++)
 {
 scanf("%d", &a[i]);
 }
 quicksort(a,0,n-1);
 printf("\n sorted array is: ");
 for(i=0;i<n;i++)
 {
 printf(" %d ",a[i]);
 }
 getch();
}
void quicksort(int a[], int first, int last)
{
 int i,j,pivot,temp;
 if(first<last)
 {
 pivot=first;
 i=first;
 j=last;
 while(i<j)
 {
while(a[i]<=a[pivot] && i<last)
{
 i++;
}
while(a[j]>a[pivot])
{
 j--;
}
if(i<j)
{
 temp=a[i];
 a[i]=a[j];
 a[j]=temp;
}
 }
 temp=a[pivot];
 a[pivot]=a[j];
 a[j]=temp;
 quicksort(a,first,j-1);
 quicksort(a,j+1,last);
 }
}
OUTPUT
Enter how many elements u want to enter: 5
Enter the 5 elemets in array: 12 2 1 34 6
sorted array is: 1 2 6 12 34
Experiment 1
Problem Statement :-
1. Write a program to input 2 numbers from the user and display their 
addition, multiplication, subtraction, and division.
import java.util.Scanner;
public class Main {
public static void main(String[] args) {
Scanner scanner = new Scanner(System.in);
// Read the first number from the user
System.out.print("Enter the first number: ");
int num1 = scanner.nextInt();
// Read the second number from the user
System.out.print("Enter the second number: ");
int num2 = scanner.nextInt();
// Calculate the sum, difference, product, and quotient of the two numbers
int sum = num1 + num2;
int difference = num1 - num2;
int product = num1 * num2;
int quotient = num1 / num2;
// Display the results
System.out.println("The sum of the two numbers is: " + sum);
System.out.println("The difference of the two numbers is: " + difference);
System.out.println("The product of the two numbers is: " + product);
System.out.println("The quotient of the two numbers is: " + quotient);
}
}
Output:-
Enter the first number: 10
Enter the second number: 5
The sum of the two numbers is: 15
The difference of the two numbers is: 5
The product of the two numbers is: 50
The quotient of the two number is: 2
Problem Statement :-
2. Write a program to accept value of marks of 5 subjects and calculate 
percentage and display it.
import java.util.Scanner;
public class CalculatePercentage {
public static void main(String[] args) {
Scanner scanner = new Scanner(System.in);
// Get the marks of 5 subjects from the user
System.out.println("Enter the marks of 5 subjects:");
int subject1 = scanner.nextInt();
int subject2 = scanner.nextInt();
int subject3 = scanner.nextInt();
int subject4 = scanner.nextInt();
int subject5 = scanner.nextInt();
// Calculate the total marks
int totalMarks = subject1 + subject2 + subject3 + subject4 + subject5;
// Calculate the percentage
float percentage = (totalMarks / 500.0f) * 100.0f;
// Display the percentage
System.out.println("The percentage is: " + percentage);
}
}
Output:-
Enter the marks of 5 subjects:
90
80
70
60
50
The percentage is: 70.0
Problem Statement :-
3. Write a program to assign value of radius then calculate the area of circle by 
using method calling (use arithmetic promotion).
import java.util.Scanner;
public class CircleAreaCalculator {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Prompt the user to enter the radius
 System.out.print("Enter the radius of the circle: ");
 double radius = scanner.nextDouble();
 // Call the method to calculate the area
 double area = calculateArea(radius);
 // Display the result
 System.out.println("The area of the circle with radius " + radius + " is: " + 
area);
 }
 // Method to calculate the area of a circle
 private static double calculateArea(double radius) {
 // Formula for the area of a circle: A = π * r^2
 double area = Math.PI * Math.pow(radius, 2);
 return area;
 }
}
Output:-
Enter the radius of the circle: 5
The area of the circle with radius 5.0 is: 78.53981633974483
Problem Statement :-
4. Write a program to calculate area of triangle and area of rectangle by using 
method calling.
import java.util.Scanner;
public class AreaCalculator {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Get input for triangle
 System.out.print("Enter the base of the triangle: ");
 double base = scanner.nextDouble();
 System.out.print("Enter the height of the triangle: ");
 double height = scanner.nextDouble();
 // Call the method to calculate the area of the triangle
 double triangleArea = calculateTriangleArea(base, height);
 // Display the result for triangle
 System.out.println("The area of the triangle with base " + base + " and height 
" + height + " is: " + triangleArea);
 // Get input for rectangle
 System.out.print("Enter the length of the rectangle: ");
 double length = scanner.nextDouble();
 System.out.print("Enter the width of the rectangle: ");
 double width = scanner.nextDouble();
 // Call the method to calculate the area of the rectangle
 double rectangleArea = calculateRectangleArea(length, width);
 // Display the result for rectangle
 System.out.println("The area of the rectangle with length " + length + " and 
width " + width + " is: " + rectangleArea);
 }
 // Method to calculate the area of a triangle
 private static double calculateTriangleArea(double base, double height) {
 // Formula for the area of a triangle: A = 0.5 * base * height
 return 0.5 * base * height;
 }
 // Method to calculate the area of a rectangle
 private static double calculateRectangleArea(double length, double width) {
 // Formula for the area of a rectangle: A = length * width
 return length * width;
 }
}
Output:-
Enter the base of the triangle: 6
Enter the height of the triangle: 8
The area of the triangle with base 6.0 and height 8.0 is: 24.0
Enter the length of the rectangle: 5
Enter the width of the rectangle: 10
The area of the rectangle with length 5.0 and width 10.0 is: 50.0
Experiment No.:
Problem Statement :-
1. Write a program to perform mathematical operations by using different 
methods of Math class.
public class MathOperations {
 public static void main(String[] args) {
 // Example values for demonstration
 double number1 = 5.4;
 double number2 = 2.6;
 // Math operations using different methods
 double sum = add(number1, number2);
 double difference = subtract(number1, number2);
 double product = multiply(number1, number2);
 double quotient = divide(number1, number2);
 double power = power(number1, 2); // 5.4^2
 double squareRoot = squareRoot(number2);
 // Display the results
 System.out.println("Sum: " + sum);
 System.out.println("Difference: " + difference);
 System.out.println("Product: " + product);
 System.out.println("Quotient: " + quotient);
 System.out.println("Power: " + power);
 System.out.println("Square Root: " + squareRoot);
 }
 // Method to add two numbers
 private static double add(double a, double b) {
 return Math.addExact((int) a, (int) b); // Example of addExact method
 }
 // Method to subtract two numbers
 private static double subtract(double a, double b) {
 return a - b;
 }
 // Method to multiply two numbers
 private static double multiply(double a, double b) {
 return Math.multiplyExact((int) a, (int) b); // Example of multiplyExact 
method
 }
 // Method to divide two numbers
 private static double divide(double a, double b) {
 return a / b;
 }
 // Method to calculate the power of a number
 private static double power(double base, double exponent) {
 return Math.pow(base, exponent);
 }
 // Method to calculate the square root of a number
 private static double squareRoot(double number) {
 return Math.sqrt(number);
 }
}
Output:-
Sum: 8.0
Difference: 2.8
Product: 10.0
Quotient: 2.076923076923077
Power: 29.16
Square Root: 1.61245154965971
Problem Statement :-
2. Write a program to accept the string from the user to perform string 
related operations by using different methods of String class.
import java.util.Scanner;
public class UserStringOperations {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accept a string from the user
 System.out.print("Enter a string: ");
 String userInput = scanner.nextLine();
 // Perform string operations using different methods
 int length = userInput.length();
 String upperCase = userInput.toUpperCase();
 String lowerCase = userInput.toLowerCase();
 String trimmedString = userInput.trim();
 boolean startsWithHello = userInput.startsWith("Hello");
 boolean endsWithWorld = userInput.endsWith("World");
 int indexOfLetterO = userInput.indexOf('o');
 String substringFromIndex5 = userInput.substring(5);
 // Display the results
 System.out.println("Length of the string: " + length);
 System.out.println("Uppercase: " + upperCase);
 System.out.println("Lowercase: " + lowerCase);
 System.out.println("Trimmed string: " + trimmedString);
 System.out.println("Starts with 'Hello': " + startsWithHello);
 System.out.println("Ends with 'World': " + endsWithWorld);
 System.out.println("Index of 'o': " + indexOfLetterO);
 System.out.println("Substring from index 5: " + substringFromIndex5);
 }
}
Output:-
Enter a string: Hello, World! 
Length of the string: 15
Uppercase: HELLO, WORLD!
Lowercase: hello, world! 
Trimmed string: Hello, World!
Starts with 'Hello': true
Ends with 'World': true
Index of 'o': 4
Substring from index 5: , World!
Experiment No.:
Problem Statement :-
1. Write a program to perform addition by changing the number of arguments 
using function overloading.
public class AdditionWithOverloading {
 public static void main(String[] args) {
 // Example with two numbers
 int sum1 = add(5, 10);
 System.out.println("Sum 1: " + sum1);
 // Example with three numbers
 int sum2 = add(15, 20, 25);
 System.out.println("Sum 2: " + sum2);
 // Example with four numbers
 int sum3 = add(30, 35, 40, 45);
 System.out.println("Sum 3: " + sum3);
 }
 // Method for adding two numbers
 private static int add(int a, int b) {
 return a + b;
 }
 // Method for adding three numbers
 private static int add(int a, int b, int c) {
 return a + b + c;
 }
 // Method for adding four numbers
 private static int add(int a, int b, int c, int d) {
 return a + b + c + d;
 }
}
Output:-
Sum 1: 15
Sum 2: 60
Sum 3: 150
Problem Statement :-
2. Write a program to perform multiplication by changing the data types using 
function overloading.
public class MultiplicationWithOverloading {
 public static void main(String[] args) {
 // Example with two integers
 int result1 = multiply(5, 10);
 System.out.println("Result 1: " + result1);
 // Example with two doubles
 double result2 = multiply(2.5, 3.5);
 System.out.println("Result 2: " + result2);
 // Example with an integer and a double
 double result3 = multiply(4, 1.5);
 System.out.println("Result 3: " + result3);
 }
 // Method for multiplying two integers
 private static int multiply(int a, int b) {
 return a * b;
 }
 // Method for multiplying two doubles
 private static double multiply(double a, double b) {
 return a * b;
 }
 // Method for multiplying an integer and a double
 private static double multiply(int a, double b) {
 return a * b;
 }
}
Output:-
Result 1: 50
Result 2: 8.75
Result 3: 6.0
Problem Statement :-
3. Write a program to declare class student having data member id and name, 
initialized it using default constructor for two object of class and display all 
records.
public class Student {
 // Data members
 private int id;
 private String name;
 // Default constructor
 public Student() {
 // Default values
 id = 0;
 name = "Unknown";
 }
 // Parameterized constructor
 public Student(int id, String name) {
 this.id = id;
 this.name = name;
 }
 // Method to display student information
 public void displayStudentInfo() {
 System.out.println("Student ID: " + id);
 System.out.println("Student Name: " + name);
 System.out.println();
 }
 public static void main(String[] args) {
 // Create two objects of the Student class using the default constructor
 Student student1 = new Student();
 Student student2 = new Student();
 // Display information for both students
 System.out.println("Student 1 Information:");
 student1.displayStudentInfo();
 System.out.println("Student 2 Information:");
 student2.displayStudentInfo();
 }
}
Output:-
Student 1 Information:
Student ID: 0
Student Name: Unknown
Student 2 Information:
Student ID: 0
Student Name: Unknown
Problem Statement :-
4. Write a program to declare class Book having data member id, name and 
price, initialized it using parameterized constructor for two object of class and 
display all records.
public class Book {
 // Data members
 private int id;
 private String name;
 private double price;
 // Parameterized constructor
 public Book(int id, String name, double price) {
 this.id = id;
 this.name = name;
 this.price = price;
 }
 // Method to display book information
 public void displayBookInfo() {
 System.out.println("Book ID: " + id);
 System.out.println("Book Name: " + name);
 System.out.println("Book Price: $" + price);
 System.out.println();
 }
 public static void main(String[] args) {
 // Create two objects of the Book class using the parameterized constructor
 Book book1 = new Book(101, "Java Programming", 29.99);
 Book book2 = new Book(102, "Data Structures and Algorithms", 39.99);
 // Display information for both books
 System.out.println("Book 1 Information:");
 book1.displayBookInfo();
 System.out.println("Book 2 Information:");
 book2.displayBookInfo();
 }
}
Output:-
Book 1 Information:
Book ID: 101
Book Name: Java Programming
Book Price: $29.99
Book 2 Information:
Book ID: 102
Book Name: Data Structures and Algorithms
Book Price: $39.99
Problem Statement :-
5. Write a program to declare class Box with data member length, width, height, 
initialized three object using different constructors and calculate Volume of Box 
and display records.
public class Box {
 // Data members
 private double length;
 private double width;
 private double height;
 // Default constructor
 public Box() {
 // Default values
 length = 1.0;
 width = 1.0;
 height = 1.0;
 }
 // Parameterized constructor with one parameter
 public Box(double side) {
 length = side;
 width = side;
 height = side;
 }
 // Parameterized constructor with three parameters
 public Box(double length, double width, double height) {
 this.length = length;
 this.width = width;
 this.height = height;
 }
 // Method to calculate the volume of the box
 public double calculateVolume() {
 return length * width * height;
 }
 // Method to display box information
 public void displayBoxInfo() {
 System.out.println("Box Dimensions:");
 System.out.println("Length: " + length);
 System.out.println("Width: " + width);
 System.out.println("Height: " + height);
 System.out.println("Volume: " + calculateVolume());
 System.out.println();
 }
 public static void main(String[] args) {
 // Create three objects of the Box class using different constructors
 Box box1 = new Box(); // Default constructor
 Box box2 = new Box(2.5); // Parameterized constructor with one 
parameter
 Box box3 = new Box(3.0, 4.0, 5.0); // Parameterized constructor with three 
parameters
 // Display information for all three boxes
 System.out.println("Box 1 Information:");
 box1.displayBoxInfo();
 System.out.println("Box 2 Information:");
 box2.displayBoxInfo();
 System.out.println("Box 3 Information:");
 box3.displayBoxInfo();
 }
}
Output:-
Box 1 Information:
Box Dimensions:
Length: 1.0
Width: 1.0
Height: 1.0
Volume: 1.0
Box 2 Information:
Box Dimensions:
Length: 2.5
Width: 2.5
Height: 2.5
Volume: 15.625
Box 3 Information:
Box Dimensions:
Length: 3.0
Width: 4.0
Height: 5.0
Volume: 60.0
Experiment No: - 4 (Control statement)
Problem Statement :-
1. Write a program to accepts three numbers from user and find largest 
number.
import java.util.Scanner;
public class FindLargestNumber {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting three numbers from the user
 System.out.print("Enter the first number: ");
 int num1 = scanner.nextInt();
 System.out.print("Enter the second number: ");
 int num2 = scanner.nextInt();
 System.out.print("Enter the third number: ");
 int num3 = scanner.nextInt();
 // Finding the largest number
 int largestNumber = findLargest(num1, num2, num3);
 // Displaying the result
 System.out.println("The largest number is: " + largestNumber);
 // Closing the scanner
 scanner.close();
 }
 // Method to find the largest number among three numbers
 private static int findLargest(int a, int b, int c) {
 if (a >= b && a >= c) {
 return a;
 } else if (b >= a && b >= c) {
 return b;
 } else {
 return c;
 }
 }
}
Output:-
Enter the first number: 25
Enter the second number: 14
Enter the third number: 36
The largest number is: 36
Problem Statement :-
2. Write a program to accept number from user and calculate factorial of given 
number.
import java.util.Scanner;
public class FactorialCalculator {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting a number from the user
 System.out.print("Enter a number: ");
 int number = scanner.nextInt();
 // Checking if the number is non-negative
 if (number < 0) {
 System.out.println("Please enter a non-negative number.");
 } else {
 // Calculating factorial
 long factorial = calculateFactorial(number);
 // Displaying the result
 System.out.println("The factorial of " + number + " is: " + factorial);
 }
 // Closing the scanner
 scanner.close();
 }
 // Method to calculate factorial of a number
 private static long calculateFactorial(int n) {
 if (n == 0 || n == 1) {
 return 1;
 } else {
 return n * calculateFactorial(n - 1);
 }
 }
}
Output:-
Enter a number: 5
The factorial of 5 is: 120
Problem Statement :-
3. Write a program to accept number from user and check number is palindrome 
or not.
import java.util.Scanner;
public class PalindromeChecker {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting a number from the user
 System.out.print("Enter a number: ");
 int number = scanner.nextInt();
 // Checking if the number is a palindrome
 if (isPalindrome(number)) {
 System.out.println(number + " is a palindrome.");
 } else {
 System.out.println(number + " is not a palindrome.");
 }
 // Closing the scanner
 scanner.close();
 }
 // Method to check if a number is a palindrome
 private static boolean isPalindrome(int n) {
 int originalNumber = n;
 int reversedNumber = 0;
 while (n > 0) {
 int digit = n % 10;
 reversedNumber = reversedNumber * 10 + digit;
 n /= 10;
 }
 return originalNumber == reversedNumber;
 }
}
Output:-
Enter a number: 121
121 is a palindrome.
Problem Statement :-
4. Write a program to accept number from user and check number is 
Armstrong or not.
import java.util.Scanner;
public class ArmstrongNumberChecker {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting a number from the user
 System.out.print("Enter a number: ");
 int number = scanner.nextInt();
 // Checking if the number is an Armstrong number
 if (isArmstrongNumber(number)) {
 System.out.println(number + " is an Armstrong number.");
 } else {
 System.out.println(number + " is not an Armstrong number.");
 }
 // Closing the scanner
 scanner.close();
 }
 // Method to check if a number is an Armstrong number
 private static boolean isArmstrongNumber(int n) {
 int originalNumber = n;
 int numberOfDigits = countDigits(n);
 int sum = 0;
 while (n > 0) {
 int digit = n % 10;
 sum += Math.pow(digit, numberOfDigits);
 n /= 10;
 }
 return originalNumber == sum;
 }
 // Method to count the number of digits in a number
 private static int countDigits(int n) {
 int count = 0;
 while (n > 0) {
 n /= 10;
 count++;
 }
 return count;
 }
}
Output:-
Enter a number: 153
153 is an Armstrong number.
Problem Statement :-
5. Write a program to accept number from user and check number is prime or 
not.
import java.util.Scanner;
public class PrimeNumberChecker {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting a number from the user
 System.out.print("Enter a number: ");
 int number = scanner.nextInt();
 // Checking if the number is a prime number
 if (isPrime(number)) {
 System.out.println(number + " is a prime number.");
 } else {
 System.out.println(number + " is not a prime number.");
 }
 // Closing the scanner
 scanner.close();
 }
 // Method to check if a number is a prime number
 private static boolean isPrime(int n) {
 if (n <= 1) {
 return false;
 }
 for (int i = 2; i <= Math.sqrt(n); i++) {
 if (n % i == 0) {
 return false;
 }
 }
 return true;
 }
}
Output:-
Enter a number: 17
17 is a prime number.
Experiment No: - 5 (Array)
Problem Statement :-
1. Write a program to accepts ‘n’ number from user to store in array and finds 
largest number in an array.
import java.util.Scanner;
public class FindLargestInArray {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting the number of elements in the array
 System.out.print("Enter the number of elements: ");
 int n = scanner.nextInt();
 // Creating an array to store the numbers
 int[] numbers = new int[n];
 // Accepting 'n' numbers from the user and storing them in the array
 for (int i = 0; i < n; i++) {
 System.out.print("Enter element " + (i + 1) + ": ");
 numbers[i] = scanner.nextInt();
 }
 // Finding the largest number in the array
 int largestNumber = findLargestInArray(numbers);
 // Displaying the entered array
 System.out.print("Entered array: ");
 displayArray(numbers);
 // Displaying the result
 System.out.println("The largest number in the array is: " + largestNumber);
 // Closing the scanner
 scanner.close();
 }
 // Method to find the largest number in an array
 private static int findLargestInArray(int[] arr) {
 if (arr.length == 0) {
 throw new IllegalArgumentException("Array is empty");
 }
 int max = arr[0];
 for (int i = 1; i < arr.length; i++) {
 if (arr[i] > max) {
 max = arr[i];
 }
 }
 return max;
 }
 // Method to display the elements of an array
 private static void displayArray(int[] arr) {
 System.out.print("[");
 for (int i = 0; i < arr.length; i++) {
 System.out.print(arr[i]);
 if (i < arr.length - 1) {
 System.out.print(", ");
 }
 }
 System.out.println("]");
 }
}
Output:-
Enter the number of elements: 5
Enter element 1: 14
Enter element 2: 8
Enter element 3: 25
Enter element 4: 10
Enter element 5: 19
Entered array: [14, 8, 25, 10, 19]
The largest number in the array is: 25
Problem Statement :-
2.Write a program accept ‘n’ number storein array and perform linear search.
import java.util.Scanner;
public class LinearSearch {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting the number of elements in the array
 System.out.print("Enter the number of elements: ");
 int n = scanner.nextInt();
 // Creating an array to store the numbers
 int[] numbers = new int[n];
 // Accepting 'n' numbers from the user and storing them in the array
 for (int i = 0; i < n; i++) {
 System.out.print("Enter element " + (i + 1) + ": ");
 numbers[i] = scanner.nextInt();
 }
 // Accepting the number to search
 System.out.print("Enter the number to search: ");
 int searchNumber = scanner.nextInt();
 // Performing linear search
 int index = linearSearch(numbers, searchNumber);
 // Displaying the entered array
 System.out.print("Entered array: ");
 displayArray(numbers);
 // Displaying the result of linear search
 if (index != -1) {
 System.out.println(searchNumber + " found at index " + index + ".");
 } else {
 System.out.println(searchNumber + " not found in the array.");
 }
 // Closing the scanner
 scanner.close();
 }
 // Method to perform linear search in an array
 private static int linearSearch(int[] arr, int target) {
 for (int i = 0; i < arr.length; i++) {
 if (arr[i] == target) {
 return i; // Return the index if the target is found
 }
 }
 return -1; // Return -1 if the target is not found
 }
 // Method to display the elements of an array
 private static void displayArray(int[] arr) {
 System.out.print("[");
 for (int i = 0; i < arr.length; i++) {
 System.out.print(arr[i]);
 if (i < arr.length - 1) {
 System.out.print(", ");
 }
 }
 System.out.println("]");
 }
}
Output:-
Enter the number of elements: 7
Enter element 1: 10
Enter element 2: 24
Enter element 3: 7
Enter element 4: 15
Enter element 5: 32
Enter element 6: 18
Enter element 7: 5
Enter the number to search: 15
Entered array: [10, 24, 7, 15, 32, 18, 5]
15 found at index 3.
Problem Statement :-
3. Write a program to accept 3x3 Matrix and calculate addition of two matrix and 
display it.
import java.util.Scanner;
public class MatrixAddition {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting the elements of the first matrix
 int[][] matrix1 = new int[3][3];
 System.out.println("Enter elements for the first matrix (3x3):");
 enterMatrixElements(scanner, matrix1);
 // Accepting the elements of the second matrix
 int[][] matrix2 = new int[3][3];
 System.out.println("Enter elements for the second matrix (3x3):");
 enterMatrixElements(scanner, matrix2);
 // Calculating the sum of the matrices
 int[][] resultMatrix = addMatrices(matrix1, matrix2);
 // Displaying the entered matrices
 System.out.println("First Matrix:");
 displayMatrix(matrix1);
 System.out.println("Second Matrix:");
 displayMatrix(matrix2);
 // Displaying the result of matrix addition
 System.out.println("Sum of the Matrices:");
 displayMatrix(resultMatrix);
 // Closing the scanner
 scanner.close();
 }
 // Method to accept elements for a matrix
 private static void enterMatrixElements(Scanner scanner, int[][] matrix) {
 for (int i = 0; i < matrix.length; i++) {
 for (int j = 0; j < matrix[0].length; j++) {
 System.out.print("Enter element at position (" + (i + 1) + ", " + (j + 1) + "): 
");
 matrix[i][j] = scanner.nextInt();
 }
 }
 }
 // Method to add two matrices
 private static int[][] addMatrices(int[][] matrix1, int[][] matrix2) {
 int[][] resultMatrix = new int[3][3];
 for (int i = 0; i < matrix1.length; i++) {
 for (int j = 0; j < matrix1[0].length; j++) {
 resultMatrix[i][j] = matrix1[i][j] + matrix2[i][j];
 }
 }
 return resultMatrix;
 }
 // Method to display a matrix
 private static void displayMatrix(int[][] matrix) {
 for (int i = 0; i < matrix.length; i++) {
 for (int j = 0; j < matrix[0].length; j++) {
 System.out.print(matrix[i][j] + "\t");
 }
 System.out.println();
 }
 System.out.println();
 }
}
Output:-
Enter elements for the first matrix (3x3):
Enter element at position (1, 1): 1
Enter element at position (1, 2): 2
Enter element at position (1, 3): 3
Enter element at position (2, 1): 4
Enter element at position (2, 2): 5
Enter element at position (2, 3): 6
Enter element at position (3, 1): 7
Enter element at position (3, 2): 8
Enter element at position (3, 3): 9
Enter elements for the second matrix (3x3):
Enter element at position (1, 1): 9
Enter element at position (1, 2): 8
Enter element at position (1, 3): 7
Enter element at position (2, 1): 6
Enter element at position (2, 2): 5
Enter element at position (2, 3): 4
Enter element at position (3, 1): 3
Enter element at position (3, 2): 2
Enter element at position (3, 3): 1
First Matrix:
1 2 3
4 5 6
7 8 9
Second Matrix:
9 8 7
6 5 4
3 2 1
Sum of the Matrices:
10 10 10
10 10 10
10 10 10
Problem Statement :-
4. Write a program to declare class Employee having data member empid, name 
and salary. Accept records for 5 employee and display that records whose salary 
is greater than 5000.
import java.util.Scanner;
class Employee {
 int empid;
 String name;
 double salary;
 // Parameterized constructor
 public Employee(int empid, String name, double salary) {
 this.empid = empid;
 this.name = name;
 this.salary = salary;
 }
}
public class EmployeeRecords {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Creating an array to store Employee objects
 Employee[] employees = new Employee[5];
 // Accepting records for 5 employees
 for (int i = 0; i < employees.length; i++) {
 System.out.println("Enter details for Employee " + (i + 1) + ":");
 System.out.print("Employee ID: ");
 int empid = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Name: ");
 String name = scanner.nextLine();
 System.out.print("Salary: ");
 double salary = scanner.nextDouble();
 // Creating an Employee object and storing it in the array
 employees[i] = new Employee(empid, name, salary);
 }
 // Displaying records of employees with salary greater than 5000
 System.out.println("\nEmployee records with salary greater than 5000:");
 displayRecordsWithSalaryGreaterThan5000(employees);
 // Closing the scanner
 scanner.close();
 }
 // Method to display employee records with salary greater than 5000
 private static void displayRecordsWithSalaryGreaterThan5000(Employee[] 
employees) {
 for (Employee employee : employees) {
 if (employee.salary > 5000) {
 System.out.println("Employee ID: " + employee.empid);
 System.out.println("Name: " + employee.name);
 System.out.println("Salary: " + employee.salary);
 System.out.println("----------------------");
 }
 }
 }
}
Output:-
Enter details for Employee 1:
Employee ID: 101
Name: John Doe
Salary: 6000
Enter details for Employee 2:
Employee ID: 102
Name: Jane Doe
Salary: 4500
Enter details for Employee 3:
Employee ID: 103
Name: Mark Smith
Salary: 7000
Enter details for Employee 4:
Employee ID: 104
Name: Emily Johnson
Salary: 5500
Enter details for Employee 5:
Employee ID: 105
Name: Michael Brown
Salary: 4800
Employee records with salary greater than 5000:
Employee ID: 101
Name: John Doe
Salary: 6000
----------------------
Employee ID: 103
Name: Mark Smith
Salary: 7000
----------------------
Employee ID: 104
Name: Emily Johnson
Salary: 5500
----------------------
Problem Statement :-
5. Write a program to declare class Product having data member id, name, price 
accepts records for 5 products and display all records and also display total price 
of products.
import java.util.Scanner; 
class Product {
 int id;
 String name;
 double price;
 // Parameterized constructor
 public Product(int id, String name, double price) {
 this.id = id;
 this.name = name;
 this.price = price;
 }
} 
public class ProductRecords {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Creating an array to store Product objects
 Product[] products = new Product[5];
 // Accepting records for 5 products
 for (int i = 0; i < products.length; i++) {
 System.out.println("Enter details for Product " + (i + 1) + ":");
 System.out.print("Product ID: ");
 int id = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Name: ");
 String name = scanner.nextLine();
 System.out.print("Price: ");
 double price = scanner.nextDouble();
 // Creating a Product object and storing it in the array
 products[i] = new Product(id, name, price);
 }
 // Displaying all product records
 System.out.println("\nAll Product records:");
 displayAllProductRecords(products);
 // Calculating and displaying the total price of products
 double totalPrice = calculateTotalPrice(products);
 System.out.println("\nTotal Price of Products: " + totalPrice);
 // Closing the scanner
 scanner.close();
 }
 // Method to display all product records
 private static void displayAllProductRecords(Product[] products) {
 for (Product product : products) {
 System.out.println("Product ID: " + product.id);
 System.out.println("Name: " + product.name);
 System.out.println("Price: " + product.price);
 System.out.println("----------------------");
 }
 }
 // Method to calculate the total price of products
 private static double calculateTotalPrice(Product[] products) {
 double total = 0;
 for (Product product : products) {
 total += product.price;
 }
 return total;
 }
}
Output:-
Enter details for Product 1:
Product ID: 101
Name: Laptop
Price: 1200.50
Enter details for Product 2:
Product ID: 102
Name: Smartphone
Price: 699.99
Enter details for Product 3:
Product ID: 103
Name: Camera
Price: 399.95
Enter details for Product 4:
Product ID: 104
Name: Headphones
Price: 89.99
Enter details for Product 5:
Product ID: 105
Name: Smartwatch
Price: 199.50
All Product records:
Product ID: 101
Name: Laptop
Price: 1200.5
----------------------
Product ID: 102
Name: Smartphone
Price: 699.99
----------------------
Product ID: 103
Name: Camera
Price: 399.95
----------------------
Product ID: 104
Name: Headphones
Price: 89.99
----------------------
Product ID: 105
Name: Smartwatch
Price: 199.5
----------------------
Total Price of Products: 2589.93

Experiment No:- 6 (Inheritance)
Problem Statement :-
1. Write a program to implement following inheritance. Assume suitable 
methods.
Superclass
 Class Name: Student
 Member variables: Roll_no, Name
Subclass:
 Class Name: Library
 Member variables: Member_No
import java.util.Scanner;
// Superclass
class Student {
 // Member variables
 int rollNo;
 String name;
 // Parameterized constructor
 public Student(int rollNo, String name) {
 this.rollNo = rollNo;
 this.name = name;
 }
 // Display method to show details of the student
 public void displayStudentDetails() {
 System.out.println("Student Details:");
 System.out.println("Roll No: " + rollNo);
 System.out.println("Name: " + name);
 }
}
// Subclass
class Library extends Student {
 // Additional member variable for the Library subclass
 int memberNo;
 // Parameterized constructor for the Library subclass
 public Library(int rollNo, String name, int memberNo) {
 // Calling the constructor of the superclass (Student)
 super(rollNo, name);
 this.memberNo = memberNo;
 }
 // Display method to show details of the student and library membership
 public void displayLibraryDetails() {
 // Calling the display method of the superclass (Student)
 displayStudentDetails();
 System.out.println("Library Member No: " + memberNo);
 }
}
public class InheritanceExample {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting details for a student
 System.out.print("Enter Student Roll No: ");
 int rollNo = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Enter Student Name: ");
 String name = scanner.nextLine();
 // Accepting library membership details
 System.out.print("Enter Library Member No: ");
 int memberNo = scanner.nextInt();
 // Creating an object of the Library subclass
 Library libraryMember = new Library(rollNo, name, memberNo);
 // Displaying details using the method of the subclass
 libraryMember.displayLibraryDetails();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Enter Student Roll No: 101
Enter Student Name: John Doe
Enter Library Member No: 5678
Student Details:
Roll No: 101
Name: John Doe
Library Member No: 5678
Problem Statement :-
2. Write a program to implement following multilevel inheritance. Assume 
suitable methods.
 a. Class Name: Student
 Member variables: Roll_no, Name
 b. Class Name: Marks
 Member variables: Marks1, Marks2, Total
 c. Class Name: Result
 Member variables: Percentage
import java.util.Scanner;
// Base class
class Student {
 // Member variables
 int rollNo;
 String name;
 // Parameterized constructor
 public Student(int rollNo, String name) {
 this.rollNo = rollNo;
 this.name = name;
 }
 // Display method to show details of the student
 public void displayStudentDetails() {
 System.out.println("Student Details:");
 System.out.println("Roll No: " + rollNo);
 System.out.println("Name: " + name);
 }
}
// Derived class 1
class Marks extends Student {
 // Member variables
 int marks1;
 int marks2;
 int total;
 // Parameterized constructor
 public Marks(int rollNo, String name, int marks1, int marks2) {
 // Calling the constructor of the base class (Student)
 super(rollNo, name);
 this.marks1 = marks1;
 this.marks2 = marks2;
 this.total = marks1 + marks2;
 }
 // Display method to show details of the student and marks
 public void displayMarksDetails() {
 // Calling the display method of the base class (Student)
 displayStudentDetails();
 System.out.println("Marks Details:");
 System.out.println("Marks 1: " + marks1);
 System.out.println("Marks 2: " + marks2);
 System.out.println("Total Marks: " + total);
 }
}
// Derived class 2
class Result extends Marks {
 // Member variable
 double percentage;
 // Parameterized constructor
 public Result(int rollNo, String name, int marks1, int marks2) {
 // Calling the constructor of the intermediate class (Marks)
 super(rollNo, name, marks1, marks2);
 this.percentage = calculatePercentage();
 }
 // Method to calculate percentage
 private double calculatePercentage() {
 return (double) super.total / 2; // Assuming total marks out of 100
 }
 // Display method to show details of the student, marks, and result
 public void displayResultDetails() {
 // Calling the display method of the intermediate class (Marks)
 displayMarksDetails();
 System.out.println("Result Details:");
 System.out.println("Percentage: " + percentage + "%");
 }
}
public class MultilevelInheritanceExample {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting details for a student
 System.out.print("Enter Student Roll No: ");
 int rollNo = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Enter Student Name: ");
 String name = scanner.nextLine();
 // Accepting marks details
 System.out.print("Enter Marks 1: ");
 int marks1 = scanner.nextInt();
 System.out.print("Enter Marks 2: ");
 int marks2 = scanner.nextInt();
 // Creating an object of the Result class
 Result studentResult = new Result(rollNo, name, marks1, marks2);
 // Displaying details using the method of the Result class
 studentResult.displayResultDetails();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Enter Student Roll No: 101
Enter Student Name: John Doe
Enter Marks 1: 75
Enter Marks 2: 85
Student Details:
Roll No: 101
Name: John Doe
Marks Details:
Marks 1: 75
Marks 2: 85
Total Marks: 160
Result Details:
Percentage: 80.0%
Experiment No:- 7 (Polymorphism)
Problem Statement :-
1. Write a Java program to create a base class Bank with method with 
interest_rate(). Create two subclasses SBI and ICICI. Override the 
interest_rate () method to find out interest rate.
import java.util.Scanner;
// Base class
class Bank {
 // Method to calculate interest rate (dummy implementation in the base class)
 public void interest_rate() {
 System.out.println("Interest Rate in the Bank class: 4%");
 }
}
// Subclass 1
class SBI extends Bank {
 // Overriding the interest_rate() method in SBI subclass
 @Override
 public void interest_rate() {
 System.out.println("Interest Rate in SBI: 5%");
 }
}
// Subclass 2
class ICICI extends Bank {
 // Overriding the interest_rate() method in ICICI subclass
 @Override
 public void interest_rate() {
 System.out.println("Interest Rate in ICICI: 6%");
 }
}
public class BankExample {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Creating objects of the subclasses
 Bank bank = new Bank();
 SBI sbi = new SBI();
 ICICI icici = new ICICI();
 // Calling the interest_rate() method for each object
 System.out.println("Calling interest_rate() method for the Bank class:");
 bank.interest_rate();
 System.out.println("\nCalling interest_rate() method for the SBI class:");
 sbi.interest_rate();
 System.out.println("\nCalling interest_rate() method for the ICICI class:");
 icici.interest_rate();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Calling interest_rate() method for the Bank class:
Interest Rate in the Bank class: 4%
Calling interest_rate() method for the SBI class:
Interest Rate in SBI: 5%
Calling interest_rate() method for the ICICI class:
Interest Rate in ICICI: 6%
Problem Statement :-
2. Write a program to declare class Shape then calculate Area of circle, Area 
of Triangle, Area of Rectangle and area of Square using Constructor 
overloading.
import java.util.Scanner;
class Shape {
 // Common variable for all shapes
 private double area;
 // Constructor for Circle
 public Shape(double radius) {
 area = calculateCircleArea(radius);
 }
 // Constructor for Triangle
 public Shape(double base, double height) {
 area = calculateTriangleArea(base, height);
 }
 // Constructor for Rectangle
 public Shape(double length, double width, String shapeType) {
 if (shapeType.equalsIgnoreCase("rectangle")) {
 area = calculateRectangleArea(length, width);
 } else if (shapeType.equalsIgnoreCase("square")) {
 area = calculateSquareArea(length);
 } else {
 System.out.println("Invalid shape type");
 }
 }
 // Method to calculate area of a circle
 private double calculateCircleArea(double radius) {
 return Math.PI * radius * radius;
 }
 // Method to calculate area of a triangle
 private double calculateTriangleArea(double base, double height) {
 return 0.5 * base * height;
 }
 // Method to calculate area of a rectangle
 private double calculateRectangleArea(double length, double width) {
 return length * width;
 }
 // Method to calculate area of a square
 private double calculateSquareArea(double side) {
 return side * side;
 }
 // Method to display the area
 public void displayArea() {
 System.out.println("Area: " + area);
 }
}
public class ShapeAreaCalculator {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Calculate area of a circle
 System.out.print("Enter radius of the circle: ");
 double radius = scanner.nextDouble();
 Shape circle = new Shape(radius);
 System.out.println("Area of Circle:");
 circle.displayArea();
 // Calculate area of a triangle
 System.out.print("\nEnter base of the triangle: ");
 double base = scanner.nextDouble();
 System.out.print("Enter height of the triangle: ");
 double height = scanner.nextDouble();
 Shape triangle = new Shape(base, height);
 System.out.println("\nArea of Triangle:");
 triangle.displayArea();
 // Calculate area of a rectangle or square
 System.out.print("\nEnter length of the rectangle or square: ");
 double length = scanner.nextDouble();
 System.out.print("Enter width of the rectangle or type 'square' for a square: 
");
 String shapeType = scanner.next();
 Shape rectangleOrSquare = new Shape(length, length, shapeType);
 System.out.println("\nArea of " + shapeType.substring(0, 1).toUpperCase() + 
shapeType.substring(1) + ":");
 rectangleOrSquare.displayArea();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Enter radius of the circle: 5
Area of Circle:
Area: 78.53981633974483
Enter base of the triangle: 4
Enter height of the triangle: 8
Area of Triangle:
Area: 16.0
Enter length of the rectangle or square: 6
Enter width of the rectangle or type 'square' for a square: square
Area of Square:
Area: 36.0
Experiment No:- 8 (Interface)
Problem Statement :-
1. Write a program to implement following inheritance. Assume suitable 
methods.
import java.util.Scanner;
// Interface Sports
interface Sports {
 // Member variables
 int wt = 5;
 // Method signature
 void show();
}
// Class Student implementing the Sports interface
class Student implements Sports {
 // Member variables
 int rollNo;
 String name;
 // Parameterized constructor
 public Student(int rollNo, String name) {
 this.rollNo = rollNo;
 this.name = name;
 }
 // Method from the Sports interface
 public void show() {
 System.out.println("Weightage for Sports: " + wt);
 }
 // Display method to show details of the student
 public void displayStudentDetails() {
 System.out.println("Student Details:");
 System.out.println("Roll No: " + rollNo);
 System.out.println("Name: " + name);
 }
}
// Class Result extending Student and implementing CalPercentage interface
class Result extends Student {
 // Member variables
 int marks1;
 int marks2;
 int totalMarks;
 double percentage;
 // Parameterized constructor
 public Result(int rollNo, String name, int marks1, int marks2) {
 // Calling the constructor of the superclass (Student)
 super(rollNo, name);
 this.marks1 = marks1;
 this.marks2 = marks2;
 this.totalMarks = marks1 + marks2;
 this.percentage = calculatePercentage();
 }
 // Method to calculate percentage
 private double calculatePercentage() {
 return (double) totalMarks / 2; // Assuming total marks out of 100
 }
 // Display method to show details of the student and result
 public void displayResultDetails() {
 // Calling the display method of the superclass (Student)
 displayStudentDetails();
 System.out.println("Result Details:");
 System.out.println("Marks 1: " + marks1);
 System.out.println("Marks 2: " + marks2);
 System.out.println("Total Marks: " + totalMarks);
 System.out.println("Percentage: " + percentage + "%");
 }
}
public class InheritanceAndInterfaceExample {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Accepting details for a student
 System.out.print("Enter Student Roll No: ");
 int rollNo = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Enter Student Name: ");
 String name = scanner.nextLine();
 // Accepting sports details
 System.out.print("Enter Marks 1 for Sports: ");
 int marks1 = scanner.nextInt();
 System.out.print("Enter Marks 2 for Sports: ");
 int marks2 = scanner.nextInt();
 // Creating an object of the Result class
 Result studentResult = new Result(rollNo, name, marks1, marks2);
 // Displaying details using the method of the Result class
 studentResult.displayResultDetails();
 // Calling the show() method from the Sports interface
 studentResult.show();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Enter Student Roll No: 101
Enter Student Name: John Doe
Enter Marks 1 for Sports: 8
Enter Marks 2 for Sports: 7
Student Details:
Roll No: 101
Name: John Doe
Result Details:
Marks 1: 8
Marks 2: 7
Total Marks: 15
Percentage: 7.5%
Weightage for Sports: 5
Problem Statement :-
2. Write a program to implement following inheritance. Assume suitable 
methods.
import java.util.Scanner;
// Interface Employee
interface Employee {
 // Member variables
 double B_salary = 0; // Basic Salary
 double HRA = 0; // House Rent Allowance
 double DA = 0; // Dearness Allowance
 // Method signature
 void show();
}
// Class Student
class Student {
 // Member variables
 int rollNo;
 String name;
 // Method to input details
 public void input() {
 Scanner scanner = new Scanner(System.in);
 System.out.print("Enter Roll No: ");
 rollNo = scanner.nextInt();
 scanner.nextLine(); // Consume the newline character
 System.out.print("Enter Name: ");
 name = scanner.nextLine();
 scanner.close();
 }
 // Method to output details
 public void output() {
 System.out.println("Student Details:");
 System.out.println("Roll No: " + rollNo);
 System.out.println("Name: " + name);
 }
}
// Class Manager extending Student and implementing Employee interface
class Manager extends Student implements Employee {
 // Member variables
 int M_id;
 double Total_Sal;
 // Method to calculate total salary
 public void CalcSalary() {
 Total_Sal = B_salary + HRA + DA;
 }
 // Method to display details
 public void displayManagerDetails() {
 // Calling the output method of the superclass (Student)
 output();
 System.out.println("Manager Details:");
 System.out.println("Manager ID: " + M_id);
 System.out.println("Total Salary: " + Total_Sal);
 }
 // Implementation of the show method from the Employee interface
 public void show() {
 System.out.println("Employee Details:");
 System.out.println("Basic Salary: " + B_salary);
 System.out.println("House Rent Allowance: " + HRA);
 System.out.println("Dearness Allowance: " + DA);
 }
}
public class InheritanceAndInterfaceExample {
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 // Creating an object of the Manager class
 Manager manager = new Manager();
 // Input details for the manager
 System.out.println("Enter Manager Details:");
 manager.input();
 // Input additional details for the manager
 System.out.print("Enter Manager ID: ");
 manager.M_id = scanner.nextInt();
 // Calculate total salary for the manager
 manager.CalcSalary();
 // Displaying details using the method of the Manager class
 manager.displayManagerDetails();
 // Calling the show() method from the Employee interface
 manager.show();
 // Closing the scanner
 scanner.close();
 }
}
Output:-
Enter Manager Details:
Enter Roll No: 101
Enter Name: John Doe
Enter Manager ID: 001
Student Details:
Roll No: 101
Name: John Doe
Manager Details:
Manager ID: 001
Total Salary: 0.0
Employee Details:
Basic Salary: 0.0
House Rent Allowance: 0.0
Dearness Allowance: 0.0
Experiment No: - 9 (Exception Handling)
Problem Statement :-
1. Write a program to create own exception (user defined exception) to 
accept no. from user and throw an exception if the number is not even.
import java.util.Scanner;
// Custom exception class
class NotEvenNumberException extends Exception {
 public NotEvenNumberException(String message) {
 super(message);
 }
}
public class CustomExceptionExample {
 // Method to accept a number and throw an exception if it's not even
 public static void checkEvenNumber(int number) throws 
NotEvenNumberException {
 if (number % 2 != 0) {
 throw new NotEvenNumberException("Error: Not an even number.");
 }
 }
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 try {
 // Accepting a number from the user
 System.out.print("Enter an even number: ");
 int userInput = scanner.nextInt();
 // Checking if the number is even
 checkEvenNumber(userInput);
 // If the number is even, display a success message
 System.out.println("Entered number is even.");
 } catch (NotEvenNumberException e) {
 // Catching the custom exception and displaying the error message
 System.out.println(e.getMessage());
 } catch (Exception e) {
 // Catching other exceptions (e.g., InputMismatchException)
 System.out.println("Error: Invalid input. Please enter an integer.");
 } finally {
 // Closing the scanner
 scanner.close();
 }
 }
}
Output:-
Enter an even number: 7
Error: Not an even number.
Enter an even number: 12
Entered number is even.
Problem Statement :-
2. Write a program to create own exception (user defined exception) to 
accept no. from user and throw an exception if the number is not Prime.
import java.util.Scanner;
// Custom exception class
class NotPrimeNumberException extends Exception {
 public NotPrimeNumberException(String message) {
 super(message);
 }
}
public class CustomExceptionExample {
 // Method to check if a number is prime
 public static boolean isPrime(int number) {
 if (number <= 1) {
 return false;
 }
 for (int i = 2; i <= Math.sqrt(number); i++) {
 if (number % i == 0) {
 return false;
 }
 }
 return true;
 }
 // Method to accept a number and throw an exception if it's not prime
 public static void checkPrimeNumber(int number) throws 
NotPrimeNumberException {
 if (!isPrime(number)) {
 throw new NotPrimeNumberException("Error: Not a prime number.");
 }
 }
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 try {
 // Accepting a number from the user
 System.out.print("Enter a prime number: ");
 int userInput = scanner.nextInt();
 // Checking if the number is prime
 checkPrimeNumber(userInput);
 // If the number is prime, display a success message
 System.out.println("Entered number is prime.");
 } catch (NotPrimeNumberException e) {
 // Catching the custom exception and displaying the error message
 System.out.println(e.getMessage());
 } catch (Exception e) {
 // Catching other exceptions (e.g., InputMismatchException)
 System.out.println("Error: Invalid input. Please enter an integer.");
 } finally {
 // Closing the scanner
 scanner.close();
 }
 }
}
Output:-
Enter a prime number: 12
Error: Not a prime number.
Enter a prime number: 7
Entered number is prime.
Problem Statement :-
3. Write a program to create own exception (user defined exception) to accept 
age from user and throw an exception if the age is negative.
import java.util.Scanner;
// Custom exception class
class NegativeAgeException extends Exception {
 public NegativeAgeException(String message) {
 super(message);
 }
}
public class CustomExceptionExample {
 // Method to accept age and throw an exception if it's negative
 public static void checkAge(int age) throws NegativeAgeException {
 if (age < 0) {
 throw new NegativeAgeException("Error: Age cannot be negative.");
 }
 }
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 try {
 // Accepting age from the user
 System.out.print("Enter your age: ");
 int userAge = scanner.nextInt();
 // Checking if the age is negative
 checkAge(userAge);
 // If the age is non-negative, display a success message
 System.out.println("Entered age is: " + userAge);
 } catch (NegativeAgeException e) {
 // Catching the custom exception and displaying the error message
 System.out.println(e.getMessage());
 } catch (Exception e) {
 // Catching other exceptions (e.g., InputMismatchException)
 System.out.println("Error: Invalid input. Please enter a valid age.");
 } finally {
 // Closing the scanner
 scanner.close();
 }
 }
}
Output:-
Enter your age: 25
Entered age is: 25
Enter your age: -5
Error: Age cannot be negative.
Problem Statement :-
4. Write a program to create own exception (user defined exception) to accept 
String from user and throw an exception if the string is not starting character ‘s’.
import java.util.Scanner;
// Custom exception class
class NotStartsWithSException extends Exception {
 public NotStartsWithSException(String message) {
 super(message);
 }
}
public class CustomExceptionExample {
 // Method to accept a string and throw an exception if it doesn't start with 's'
 public static void checkStartsWithS(String input) throws 
NotStartsWithSException {
 if (!input.toLowerCase().startsWith("s")) {
 throw new NotStartsWithSException("Error: String must start with 's'.");
 }
 }
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 try {
 // Accepting a string from the user
 System.out.print("Enter a string starting with 's': ");
 String userInput = scanner.nextLine();
 // Checking if the string starts with 's'
 checkStartsWithS(userInput);
 // If the string starts with 's', display a success message
 System.out.println("Entered string is: " + userInput);
 } catch (NotStartsWithSException e) {
 // Catching the custom exception and displaying the error message
 System.out.println(e.getMessage());
 } catch (Exception e) {
 // Catching other exceptions
 System.out.println("Error: Invalid input. Please enter a valid string.");
 } finally {
 // Closing the scanner
 scanner.close();
 }
 }
}
Output:-
Enter a string starting with 's': Summer
Entered string is: Summer
Enter a string starting with 's': Rainy
Error: String must start with 's'.
Problem Statement :-
5. Write a program to create own exception (user defined exception) to accept 
Password from user and throw an “AuthenticationFailure” exception if the 
password is incorrect.
import java.util.Scanner;
// Custom exception class
class AuthenticationFailureException extends Exception {
 public AuthenticationFailureException(String message) {
 super(message);
 }
}
public class CustomExceptionExample {
 // Method to authenticate the password and throw an exception if it's incorrect
 public static void authenticatePassword(String password) throws 
AuthenticationFailureException {
 // Here, you can define your own conditions for a valid password
 // For simplicity, let's assume a valid password is "securepassword"
 if (!password.equals("securepassword")) {
 throw new AuthenticationFailureException("Error: Authentication failure. 
Incorrect password.");
 }
 }
 public static void main(String[] args) {
 Scanner scanner = new Scanner(System.in);
 try {
 // Accepting a password from the user
 System.out.print("Enter your password: ");
 String userPassword = scanner.nextLine();
 // Authenticating the password
 authenticatePassword(userPassword);
 // If the password is correct, display a success message
 System.out.println("Authentication successful.");
 } catch (AuthenticationFailureException e) {
 // Catching the custom exception and displaying the error message
 System.out.println(e.getMessage());
 } catch (Exception e) {
 // Catching other exceptions
 System.out.println("Error: Invalid input. Please enter a valid password.");
 } finally {
 // Closing the scanner
 scanner.close();
 }
 }
}
Output:-
Enter your password: securepassword
Authentication successful.
Enter your password: incorrectpassword
Error: Authentication failure. Incorrect password.
Experiment No: - 10 (Package)
• java.lang: This package contains fundamental classes that are automatically 
imported into every Java program. It includes classes like String, Object, and basic 
data types.
• java.util: This package contains utility classes and data structures like lists, sets, 
maps, and more. It includes the ArrayList, HashMap, LinkedList, etc.
• java.io: This package provides classes for input and output operations. It includes 
classes for reading and writing files, working with streams, and handling 
serialization.
• java.net: This package contains classes for networking, including sockets, URLs, 
and network protocols. It's used for developing network applications.
• java.awt: This package provides classes for creating graphical user interfaces (GUI). 
It includes components like buttons, frames, and layout managers.
• javax.swing: Building on java.awt, this package provides additional GUI 
components and features. It includes components like JFrame, JButton, and more.
• java.sql: This package provides classes and interfaces for database connectivity. 
It's used for interacting with relational databases using Java Database Connectivity 
(JDBC).
• java.text: This package provides classes for formatting and parsing text, dates, and 
numbers. It includes classes like SimpleDateFormat and DecimalFormat.
• java.time: Introduced in Java 8, this package contains classes for handling dates 
and times in a more comprehensive and flexible way compared to the older 
java.util.Date and java.util.Calendar classes.
• java.nio: This package provides support for non-blocking I/O operations and 
improved file system handling. It includes classes like Path, Files, and Channels.
Experiment No: - 11
Problem Statement :-
Write a javascript program on client side scripting.
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Client-Side Scripting with JavaScript</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 text-align: center;
 margin: 50px;
 }
 </style>
</head>
<body>
 <h1>Client-Side Scripting with JavaScript</h1>
 <button id="clickButton">Click Me!</button>
 <script>
 // JavaScript code for client-side scripting
 // Function to be executed when the button is clicked
 function handleClick() {
 // Display an alert
 alert('Button Clicked!');
 }
 // Get the button element by its ID
 var button = document.getElementById('clickButton');
 // Attach the handleClick function to the button's click event
 button.addEventListener('click', handleClick);
 </script>
</body>
</html>
Experiment No: - 12
Problem Statement :-
Write a JavaScript program on User Defined Function.
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>User Defined Function in JavaScript</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 text-align: center;
 margin: 50px;
 }
 </style>
</head>
<body>
 <h1>User Defined Function in JavaScript</h1>
 <label for="lengthInput">Enter Length of Rectangle:</label>
 <input type="number" id="lengthInput" placeholder="Length">
 <label for="widthInput">Enter Width of Rectangle:</label>
 <input type="number" id="widthInput" placeholder="Width">
 <button onclick="calculateArea()">Calculate Area</button>
 <p id="resultArea"></p>
 <script>
 // JavaScript code with user-defined functions
 // Function to calculate the area of a rectangle
 function calculateRectangleArea(length, width) {
 return length * width;
 }
 // Function to be executed when the button is clicked
 function calculateArea() {
 // Get user input values
 var length = parseFloat(document.getElementById('lengthInput').value);
 var width = parseFloat(document.getElementById('widthInput').value);
 // Check if the input is valid
 if (isNaN(length) || isNaN(width)) {
 alert('Please enter valid numeric values for length and width.');
 return;
 }
 // Call the user-defined function to calculate the area
 var area = calculateRectangleArea(length, width);
 // Display the result
 document.getElementById('resultArea').textContent = 'Area of the 
rectangle: ' + area;
 }
 </script>
</body>
</html>
Experiment No: - 13
Problem Statement :-
Write a JavaScript program on validation using object function.
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Form Validation using Object and Functions</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 text-align: center;
 margin: 50px;
 }
 .error {
 color: red;
 }
 </style>
</head>
<body>
 <h1>Form Validation using Object and Functions</h1>
 <form id="registrationForm" onsubmit="validateForm(); return false;">
 <label for="name">Name:</label>
 <input type="text" id="name" placeholder="Enter your name">
 <br>
 <label for="email">Email:</label>
 <input type="email" id="email" placeholder="Enter your email">
 <br>
 <label for="password">Password:</label>
 <input type="password" id="password" placeholder="Enter your password">
 <br>
 <button type="submit">Submit</button>
 </form>
 <div id="errorMessages" class="error"></div>
 <script>
 // JavaScript code for validation using object and functions
 // Object to hold validation functions
 var validator = {
 validateName: function(name) {
 return /^[a-zA-Z\s]+$/.test(name);
 },
 validateEmail: function(email) {
 // Basic email validation for demonstration purposes
 return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
 },
 validatePassword: function(password) {
 // Basic password validation for demonstration purposes
 return password.length >= 6;
 }
 };
 // Function to validate the form
 function validateForm() {
 // Get form input values
 var name = document.getElementById('name').value.trim();
 var email = document.getElementById('email').value.trim();
 var password = document.getElementById('password').value;
 // Clear previous error messages
 document.getElementById('errorMessages').textContent = '';
 // Validate name
 if (!validator.validateName(name)) {
 document.getElementById('errorMessages').textContent += 'Invalid 
name. ';
 }
 // Validate email
 if (!validator.validateEmail(email)) {
 document.getElementById('errorMessages').textContent += 'Invalid 
email. ';
 }
 // Validate password
 if (!validator.validatePassword(password)) {
 document.getElementById('errorMessages').textContent += 'Invalid 
password (should be at least 6 characters). ';
 }
 // Display success message if no errors
 if (document.getElementById('errorMessages').textContent === '') {
 alert('Form submitted successfully!');
 }
 }
 </script>
</body>
</html>
