//............Railway reservetion...............

#include <bits/stdc++.h>

using namespace std;

class Node
{
    public:
      int seatNo ;
      string name;
      string age;
      string gender;
      
      Node *next;
};

class Queue
{
    private:
    
    int front = -1;
    int rear = -1 ;
    Node *tail = NULL;
    Node *head = NULL;
    
    int n = 5;
    
    public:
    
    
    void enQueue( string p_name , string p_age , string p_gender)
    {
        if(rear == (n-1) )
        {
            cout<<"\n"<<"Seats in tarin is FULL";
            return;
        }
        else
        {
            if(rear == front == -1)
            {
                rear++;
                front++;
            }
            else
            {
                rear++;
            }
            Node *curr = (Node*) malloc(sizeof(Node));
            
            curr->seatNo = rear + 1;
            curr->name  = p_name;
            curr->age   = p_age ;
            curr->gender= p_gender;
            
            curr->next = NULL;
            
            if(rear == front == 0)
            {
                head = curr;
                tail = curr;
            }
            else
            {
                tail->next = curr;
                tail = curr;
            }
            
            cout<<"\n"<<"Your Railway reservetion is Done ";
        }
    }
    
    void deQueue()
    {
        if((rear > front) || (rear == front == -1))
        {
            cout<<"\n"<<"train is empty";
            return ;
        }
        else
        {
            Node *temp = head;
            front++;
            head = head->next;
            delete (temp);
        }
    }
    
    Node *top()
    {
        if((rear > front) || (rear == front == -1))
        {
            cout<<"\n"<<"train is empty";
            return NULL;
        }
        else
        {
            return head ;
        }
    }
    
    bool Empty()
    {
        if((rear > front) || (rear == front == -1))
        {
            cout<<"\n"<<"train is empty";
            return true;
        }
        else
        {
            cout<<"\n"<<"train is not empty";
            return false;
        }
    }
    
    void Available()
    {
        if(n-(rear+1) == 0)
        {
            cout<<"\n"<<"Seats in tarin is FULL";
            return;
        }
        else
        {
            cout<<"\n"<<"Available seat in Train is : "<<n-(rear+1);
            return;
        }
    }
    
};
int main()
{
    int x;
    Queue obj;
    
    cout<<"********Railway reservetion********";

    cout<<"\n"<<"Enter a Number for Railway reservetion : ";
    cout<<"\n"<<"a) Enter '1' for Booking";
    cout<<"\n"<<"b) Enter '2' for Available seat in Train ";
    cout<<"\n"<<"c) Enter '3' for Countine booking";
    cout<<"\n"<<"c) Enter '4' for Exite";
    cout<<"\n";
    cin>>x;
    //cout<<"\n"<<x;
    
    while(x < 5)
    {
        if(x == 1)
        {
            string p_name ;
            string p_age  ;
            string p_gender ;
            
            cout<<"\n";
            
            cout<<"\n"<<"Passenger Name : ";
            cin>>p_name;
            //cout<<"\n"<<p_name;
            
            cout<<"\n"<<"Passenger Age : ";
            cin>>p_age;
            //cout<<"\n"<<p_age;
            
            cout<<"\n"<<"Passenger Gender : ";
            cin>>p_gender;
            //cout<<"\n"<<p_gender;
            
            obj.enQueue(p_name ,p_age ,p_gender );
            
            cout<<"\n";
            cout<<"\n"<<"Enter a Number for Railway reservetion : ";
            cout<<"\n"<<"a) Enter '1' for Booking";
            cout<<"\n"<<"b) Enter '2' for Available seat in Train ";
            cout<<"\n"<<"c) Enter '3' for Countine booking";
            cout<<"\n"<<"c) Enter '4' for Exite";
            cout<<"\n";
            cin>>x;
            //cout<<"\n"<<x;
        }
        
        if(x == 2)
        {
            cout<<"\n";
            obj.Available();
            
            cout<<"\n";
            cout<<"\n"<<"Enter a Number for Railway reservetion : ";
            cout<<"\n"<<"a) Enter '1' for Booking";
            cout<<"\n"<<"b) Enter '2' for Available seat in Train ";
            cout<<"\n"<<"c) Enter '3' for Countine booking";
            cout<<"\n"<<"c) Enter '4' for Exite";
            cout<<"\n";
            cin>>x;
            //cout<<"\n"<<x;
            
        }
        
        if(x == 4)
        {
            cout<<"\n"<<"Thank you";
            break; 
        }
        
        if(x == 3)
        {
            //cout<<"\n"<<"Given Number is Wrong (outoff range)";
            
            cout<<"\n";
            cout<<"\n"<<"Enter a Number for Railway reservetion : ";
            cout<<"\n"<<"a) Enter '1' for Booking";
            cout<<"\n"<<"b) Enter '2' for Available seat in Train ";
            cout<<"\n"<<"c) Enter '3' for Countine booking";
            cout<<"\n"<<"c) Enter '4' for Exite";
            cout<<"\n";
            cin>>x;
            //cout<<"\n"<<x;
        }
    }
    
}
