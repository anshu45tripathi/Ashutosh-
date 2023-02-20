# Ashutosh-
#include<iostream>
#include<fstream>
using namespace std;
class student 
{
    int roll ;
    char name[20];
    float marks;
    void get_data ()
    {
        cout <<"\n\n enter the roll.=";
        cin>>roll;
        cout<<"\n\n enter the name =";
        cin>>name;
        cout<<"\n\n enter the marks";
        cin>>marks;
    }
    public :
    void addrecord()
    {
        fstream f;
        student st;
        f.open ("student .dat",ios::app|ios::binary );
        st.get_data();
        f.write ((char*)&st,sizeof(st));
        f.close();

    }
};
int main()
{
    student s;
    char ch='n';
    do 
    {
        s.addrecord();
        cout<<"\n do you want to add another data (y/n): ";
        ch=getchar();
    }
    
    while(ch=='y'||ch=='Y');
    {
    cout<<"\n\ndata written successfully.......";
    }
    return 0;

    
    }
