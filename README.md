# impelement-queue-using-array
1.enqueue 2.dequeue 3.display
#include <stdio.h>
#include<stdlib.h>
#define n 5
int que[n];
int front =-1,rear=-1;
void enque();
void deque();
void display();
void main()
{
    int ch,d,y;

    do{
       printf("\n Enter choice :");
       printf("\n 1.Insert \n 2.Delete \n 3.Display \n");
        scanf("%d",&ch);
        switch(ch)
       {
           case 1:/* printf("\n Enter data :");
                   scanf("%d",&d);*/
                   enque();
                   break;
           case 2:  deque();
                   /*printf("\n data deleted is %d",d);*/
                   break;
           case 3 : display();
                    break;
       }
       printf("\n Do you want to continue ?(0/1)");
       scanf("%d",&y);

    }
    while(y==1);

}

void enque()
{
    int d;
    printf("enter data:\n");
    scanf("%d",&d);
    if(rear==n-1)
    {
        printf("overflow\n");
    }
    else if(front==-1 && rear==-1)
    {
        rear++;
        que[rear]=d;
        front=rear;
    }
    else {
        rear++;
        que[rear]=d;
    }
}
void deque()
{
    int e;
    if(front==-1){
        printf("underflow\n");
    
    }
    else if(front==rear){
        e=que[front];
        front =-1;
        rear=-1;
    }
    else {
        e=que[front];
        front++;
    }
}
void display()
{
    if(front==-1){
        printf("empty\n");
        
    }
    else {
        printf("elements\n");
        for(int i=front;i<=rear;i++)
        {
            printf(" %d",que[i]);
        }
    }
}
