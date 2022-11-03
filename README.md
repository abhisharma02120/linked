//linked
include <iostream>
#include <stdlib.h>
using namespace std;
class a
{
	public:
	struct node{
		int data;
		struct node *next;
	};
	struct node *start=NULL;
	void create()
	{
		struct node *ptr, *temp; int n;
		ptr=(struct node *) malloc(sizeof(struct node));
		cout<<"enter value:";
		cin>>n;
		ptr->data=n;
		ptr->next=NULL;
		if(start==NULL){
			start=ptr;
		}
		else{
			temp=start;
			while(temp->next!=NULL)
			{
				temp=temp->next;
			}
			temp->next=ptr;
		}}
		void display()
		{
			struct node *temp;
			if(start==NULL){
				cout<<"List is empty\n";
			}
			else{
				temp=start;
				while(temp!=NULL){
					cout<<temp->data;
					temp=temp->next;
				}
			}
		}
		void insert_beg(){
			struct node * ptr;int n;
			ptr=(struct node *) malloc(sizeof(struct node));
			cout<<"Enter value: ";
			cin>>n;
			ptr->next=NULL;
			ptr->next=start;
			start=ptr;
		}
		void delete_beg(){
			struct node * temp;
			temp = start;
			start=start->next;
			free(temp);
		}
		void del_end(){
			struct node * temp, * temp1;
			if(start==NULL){
				cout<<"List is empty";
			}
			else if(start->next==NULL){
				temp=start;
				start=NULL;
				free(temp);
			}
			else{
				temp=start;
				while(temp->next!=NULL){
					temp1 = temp;
					temp = temp->next;
				}
				temp1->next=NULL;
				free(temp);
			}
		}
		void insert_pos(){
			struct node * ptr, * temp; int n, pos, i;
			ptr=(struct node *) malloc(sizeof(struct node));
			cout<<"Enter the position in list: ";
			cin>>pos;
			cout<<"Enter the element: ";
			cin>>n;
			ptr->data=n;
			ptr->next=NULL;
			for(i=1,temp=start;i<pos;i++){
				if(temp==NULL){
					cout<<"Out of list";
				}
				else{
					temp=temp->next;
				}
			} 
			ptr->next=temp->next;
			temp->next=ptr;
		}
	void del_pos(){
		struct node * temp, * temp1; int pos, i;
		for(i=1,temp=start;i<pos;i++){
			temp1=temp;
			temp=temp->next;
		}
		temp1=temp->next;
		free(temp);
	}	
	};

int main() {
     int num;
     while(1){
     cout << "1. CREATE\n";
     cout<<"2. DISPLAY\n";
     cout<<"3. INSERT_BEG\n";
     cout<<"4. INSERT_POS\n";
     cout<<"5. INSERT_END\n";
     cout<<"6. DELETE_BEG\n";
     cout<<"7. DELETE_POS\n";
     cout<<"8. DELETE_END\n";
     cout<<"9. EXIT\n";
    
    cout << "Enter a number ";
    cin >> num;
    a o1;
    switch (num) {
        case 1:
            o1.create();
            break;
        case 2:
            o1.display();
            break;
        case 3:
            o1.insert_beg();
            break;
        case 4:
            o1.insert_pos();
            break;
         case 5:
            o1.create();
            break;
         case 6:
            o1.delete_beg();
            break;
         case 7:
            o1.del_pos();
            break;
         case 8:
            o1.del_end();
            break;
         default:
         exit(5);
         	break;
}
}}
