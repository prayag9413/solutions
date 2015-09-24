# solutions
#include<stdio.h>
#include<iostream>
#include<cstring>
#include<string>
#include<string.h>
using namespace std;

int main()
{
    char str[100010],str1[100100];
    int x, n1,i,j,flag;
    char arr[30];
    int cnt,even;
    cnt=even=flag=0;
    cin>>str;
    strcpy(str1,str);
    n1=strlen(str);
    for(i=0;i<30;i++)
        arr[i]='0';
    for(i=0;i<n1;i++)
    {
        cnt=0;
        x=str[i]-'a';
        if(arr[x]!=1)
        {
        arr[x]=1;
        for(j=i;j<n1;j++)
        {
            if(str[i] == str1[j])
            {
                cnt++;

                str1[j] = 0;
            }

        }
        }
        if(cnt %2 != 0 && cnt!=0)//|| cnt % 2 == 1)
           flag++;
        /*else if(cnt % 2 != 0)
        {
            odd++;
        }*/
        if(flag==2)
            break;

    }
    if(flag == 2)
    cout<<"NO"<<endl;
    else
        cout<<"YES"<<endl;

}
