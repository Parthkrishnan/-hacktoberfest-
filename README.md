# -hacktoberfest-

data structure
#include<stdio.h> 
#include<stdlib.h>
#include<maths.h>
void create();
void display();
void insertAtBeg();
void insertAtMid();
void insertAtLast();

 struct node 
{
	int data;
	struct node *next;
};

struct node *head=NULL;

int main()
{
	int p;
	do{	
   int ch;
   printf("\n Enter your choice");
   printf("\n Enter 1:create() 2:display()/* 3:inserttBeg() 4:insertAtMid() 5: inserAtLast()*/");
   scanf("%d",&ch);
   
   switch(ch)
   { 
   	case 1: create();
   	         break;
   	case 2: display();
   	         break;
   	case 3:  insertAtBeg();
   	         break;
   	case 4:  insertAtMid();
   	         break;
   	case 5: insertAtLast();
   	         break;
   	default: printf("\n You have entered the wrong choice\n");
   }
   printf("\n Do you want to continue, type 1 for continue and any other for not\n ");
   scanf("%d",&p);
}while(p==1);
	
	return 0;
}



void create()
{
	int m,ch;
	struct node *temp,*ptr;
	  
	do{
		printf("\n Enter the data that tou want");
		scanf("%d",&m);
		temp=(struct node*) malloc(sizeof(struct node));
		printf("\n %u",temp);
		temp->data=m;
		temp->next=NULL;
		
		if(head==NULL)
		{
			head=temp;
		}
		else
		{
			ptr=head;
			while(ptr->next!=NULL)
 			ptr=ptr->next;
			ptr->next=temp;
		}
		printf("\n For more nodes to insert type 1");
		scanf("%d",&ch);
	}while(ch==1);
}

void display()
{
	struct node *ptr;
	ptr=head;
	while(ptr!=NULL)
	{
		printf("%d->",ptr->data);
		ptr=ptr->next;
	}
	
}
	
		void insertAtBeg()
	{
		int m;
		struct node *temp;
		printf("\n Enter the data that you want at the beginning  ");
		scanf("%d",&m);
		temp=(struct node*)malloc(sizeof(struct node));
		temp->data=m;
		temp->next=head;
		head=temp;
		
	}
	
	void insertAtMid()
	{
		int m,k;
		struct node *temp,*ptr;
		printf("\n Enter the data that you want to insert and also enter the data after which it should be inserted  ");
		scanf("%d %d",&m,&k);
		temp=(struct node*)malloc(sizeof(struct node));
		temp->data=m;
		ptr=head;
	 	while(ptr->data!=k)
		ptr=ptr->next;
		temp->next=ptr->next;
		ptr->next=temp;
		
	}
	void insertAtLast()
	{
		int m;
		struct node *temp,*ptr;
		printf("\n Enter the data that you want to insert at last  ");
		scanf("%d ",&m);
		temp=(struct node*)malloc(sizeof(struct node));
		temp->data=m;
		ptr=head;
		while(ptr->next!=NULL)
		ptr=ptr->next;
		ptr->next=temp;
		temp->next=NULL;
		
 	}  
