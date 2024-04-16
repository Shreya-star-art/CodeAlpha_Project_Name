#include<iostream>
#include<windows.h>
using namespace std;
void print_tasks(string tasks[], int task_count)
{
    cout<<"TASKS TO DO :"<<endl;
    cout<<"___________________________________"<<endl;
    for(int i=0; i<task_count; i++)
    {
        cout<<"Task"<<i<<":"<<tasks[i]<<endl;
    }
    cout<<"_____________________________________"<<endl;
}
int main()
{
    system("color a");
    string tasks[10]={""};
    //Counter var-> know how many tasks we have
    int task_count=0;

    int option=-1;
    while(option!=0)
    {
        //We will make menu here.
        cout<<"___TO DO LIST___"<<endl;
        cout<<"1-TO ADD NEWTASK"<<endl;
        cout<<"2-TO VIEW TASKS"<<endl;
        cout<<"3-DELETE THE TASKS"<<endl;
        cout<<"0-TERMINATE THE PROGRAM"<<endl;
        
        cin>>option;
        switch(option)
        {
            case 1 :
            {
                if(task_count>9)
                {
                    cout<<" TASK LIST IS FULL "<<endl;
                }
                else{
                    cout<<"Enter a New Task:";
                    cin.ignore();
                    getline(cin, tasks[task_count]);
                    task_count++;                }
            }
            break;
            case 2:{
            system("cls");
            print_tasks(tasks, task_count);
            } 
            break;
            case 3:
            {
                system("cls");
                int del_task =0;
                cout<<"Enter a Task to Delete:";
                cin>>del_task;
                if(del_task<0 || del_task>9){
                    cout<<"You Entered Invalid Task No"<<endl;
                    break;
                }
                for(int i =del_task; i<task_count; i++){
                    tasks[i]=tasks[i+1];
                }
                task_count = task_count -1;
                break;
                }
                case 0:
                cout<<"TERMINATING THE PROGRAM----------"<<endl;
                break;
                default:
                cout<<"YOU ENTERED INVALID VALUE"<<endl;
        }
    }
    return 0;
}
