# solutions anagram
#include<iostream>
#include<stdio.h>
#include<cstring>
#include<string>
#include<string.h>

using namespace std;
int main()
{
    char str[100000];
    char str1[1000];
    char str2[1000];
    int t;
    cin>>t;
    while(t--)
    {
        int len,n1,n2,i,j,cnt=0,flag;
        cin>>str;
        fflush(stdin);
        len = strlen(str);

        if(len % 2 != 0)
            cout<<"-1"<<endl;
        else
        {
            n1 = n2 =len/2;

            for(i=0;i<n1;i++)
                str1[i] = str[i];

            for(i=0,j=n2;i<n2,j<len;i++,j++)
                str2[i] = str[j];

            for(i=0;i<n1;i++)
            {   flag = 0;
                for(j=0;j<n2;j++)
                {
                    if(str1[i] == str2[j])
                       {
                           flag = 1;
                           str2[j] = 0;
                           break;
                       }
                }
                if(flag == 0)
                    cnt++;
            }
           /* for(i=0;i<n2;i++)
            {
                if(str2[j] != 0)
                    cnt++;
            }*/
           cout<<cnt<<endl;
           str1[0] = '\0';
           str2[0] = '\0';
           //str[0] = '\0';
        }
    }
    return 0;
}
