# Phone-Management-System-Link-list-
// PHONEBOOK MANAGEMENT SYSTEM.cpp : Defines the entry point for the console application.
//
#include "stdafx.h" #include<iostream> #include<string> using namespace std; class Phone_Book
{
private: struct node
{
 
}*head; public:
 
int id;
string first_name; string last_name; string phone_number; node *next;
 
Phone_Book()
{
head=NULL;
}
void add_record()
{
node*q=head; node *p=new node;
cout<<"\tEnter ID: "; cin>>p->id;
cout<<"\tEnter First Name: "; cin>>p->first_name; cout<<"\tEnter Last Name: "; cin>>p->last_name; cout<<"\tEnter Phone Number: "; cin>>p->phone_number; if(head==NULL)
{
 
}
else
{
 
head=p;
p-	>next=NULL;

while(q->next!=NULL)
{
 
q=q->next;
}
q->next=p;
p->next=NULL;
}
sort();
}
void sort()
{
node *p, *q; int id;
string first_name;
 
string last_name; string phone_number; int t_id;
string t_first_name, t_last_name; string t_phone_number;
p=head; q=head; while(p!=NULL)
{
q=p->next; while(q!=NULL)
{
if(p->id>q->id)
{
t_id=p->id;
t_first_name=p->first_name; t_last_name=p->last_name; t_phone_number=p->phone_number;

p->id=q->id;
p->first_name=q->first_name; p->last_name=q->last_name;
p-	>phone_number=q->phone_number;

q-	>id=t_id;
q->first_name=t_first_name; q->last_name=t_last_name;
q->phone_number=t_phone_number;
}
q=q->next;
}
p=p->next;
}
}
void delete_record()
{
int id;
int found=0;
cout<<"\tEnter ID you want to delete: "; cin>>id;
node *p,*q; p=head; if(p==NULL)
cout<<"No record found\n"; else if(p->id==id)
{

}
else
{

head=head->next; delete p; found=1;

while(p->next!=NULL)
{
 
q=p;
p=p->next; if(p->id==id)
{
 
q->next=p->next; delete p; found=1;
break;
}
}
}
if(found==1)
{
cout<<"Record of this ID has been deleted\n";
}
else
cout<<"Record of this ID has not been found\n";
}
void display()
{
node *p; p=head; if(head==NULL)
cout<<"No records\n"; while(p!=NULL)
{
cout<<"\tID: "<<p->id<<endl;
cout<<"\tFirst Name: "<<p->first_name<<endl; cout<<"\tLast Name: "<<p->last_name<<endl; cout<<"\tPhone Number: "<<p->phone_number<<endl; cout<<endl;
p=p->next;
}
}
void search()
{
int id;
cout<<"Enter ID you want to search "; cin>>id;
int found=0; node *p=head; while(p!=NULL)
{
if(p->id==id)
{
found=1; break;
}
p=p->next;
}
if(found==1)
{

}
else
{

}
}
 
cout<<"\tID: "<<p->id<<endl;
cout<<"\tFirst Name: "<<p->first_name<<endl; cout<<"\tLast Name: "<<p->last_name<<endl; cout<<"\tPhone Number: "<<p->phone_number<<endl;



cout<<"Record not found\n"<<endl;
 
void edit()
{
int id, found=0; node *p; p=head;
cout<<"Enter ID you want to edit: "; cin>>id;
while(p!=NULL)
{
if(p->id==id)
{
found=1; break;
}
p=p->next;
}
if(found==1)
{

}
else

}
};
 
cout<<"\tEnter New ID: "; cin>>p->id;
cout<<"\tEnter New First Name: "; cin>>p->first_name; cout<<"\tEnter New Last Name: "; cin>>p->last_name;
cout<<"\tEnter New Phone Number: "; cin>>p->phone_number;

cout<<"No record found'n";
 
int _tmain(int argc, _TCHAR* argv[])
{
Phone_Book p; char i;
int choice; do{
cout<<"*****PHONE BOOK MANAGEMENT SYSTEM*****"<<endl; cout<<" 1).ADD RECORD"<<endl;
cout<<" 2).DELETE RECORD"<<endl; cout<<" 3).DISPLAY RECORD"<<endl; cout<<" 4).SEARCH RECORD"<<endl; cout<<" 5).EDIT RECORD"<<endl;
cout<<"*****ENTER YOUR OWN CHOICE*****"<<endl; cin>>choice;
switch(choice)
{
case 1:
p.add_record(); break;
case 2:
p.delete_record(); break;
case 3:
p.display(); break;
case 4:
p.search();
 
break; case 5:
p.edit(); break;
default:
cout<<"Invalid Choice"<<endl;
}
cout<<"Do you want to see the main menu?\n"; cout<<"Enter y : \n";
cin>>i;
}while(i=='y'); return 0;
}
