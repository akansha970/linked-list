# linked-list
#include<stdio.h>
#include<conio.h>

struct node
{
    int data;
    struct node *next;
};

void push(struct node**head_ref , int new_data)
{
    struct node*new_node=(struct node*)malloc(sizeof(struct node));
    new_node->data=new_data;
    new_node->next=(*head_ref);
    (*head_ref)=new_node;

}

void printList(struct node*node)
{
    while(node!=NULL)
    {
        printf("%d\n",node->data);
        node=node->next;
    }
}

int main()
{
    struct node*head=NULL;
    while(1)
    {
        int op;
        int ch;
        printf("choose the below options\n");
        printf("1.push\n");
        printf("2.display\n");
        printf("3.exit\n");
        scanf("%d",&op);
        switch(op)
        {
            case 1: printf("enter element to be pushed :");
                    scanf("%d",&ch);
                    push(&head,ch);
                    break;
                   
                   
            case 2: printf("\ncreated linked list is :");
                    printList(head);
                    break;
                   
            case 3: exit(0);


        }
       
    }
    return 0;
}
