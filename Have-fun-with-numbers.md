![description](http://i1.ciimg.com/1949/00b9b505a84b11e4.png)

```C
#include<stdio.h>
#include<string.h>
int main()
{
    char src[20];
    int dst[20];
    int cnt1[20]={0},cnt2[20]={0};
    scanf("%s",&src);
    int i,j,w,k=0,flag=1,t=0,tmp;
    for (i=strlen(src)-1;i>=0;i--)
    {
        tmp=src[i]-'0';
        cnt1[tmp]++; 
        j=2*tmp+k;   
        w=j%10;      
        k=j/10;      
        dst[i]=w;   
        cnt2[w]++;  
    }
    if (k!=0){
        t=strlen(src);
        dst[t]=k;
        cnt2[k]++;
        flag=0;
        }
    if (flag)
    {
        for (i=0;i<10;i++)
        {
            if (cnt1[i]!=cnt2[i])
            {
                flag=0;
                break;
            }
        }
    }
    if (flag==0)printf("No\n");
    else printf("Yes\n");

    if (t==strlen(src))printf("%d",dst[t]);
    for (t=0;t<strlen(src);t++)printf("%d",dst[t]);
    return 0;
}
```

source：http://www.cnblogs.com/wuxiaotianC/p/6368310.html