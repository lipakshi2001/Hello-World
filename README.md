#include<stdio.h>
void check(int a[][3]);
void playgame(int a[][3]);
void instruct()
{
    printf("                                  welcome to TIC TAC TOE                    \n");
    printf("player 1:ZERO\n");
    printf("player 2:Cross");
}
void display()
{
printf("\n         |---|---|---|\n         |---|---|---|\n         |---|---|---|           ");
}
int main()
{
   int i,j;
   int arr[3][3];
   for(i=0;i<3;i++)
   {
       for(j=0;j<3;j++)
       arr[i][j]=0;
   }
   instruct();
   display();
   playgame(arr);
}
void playgame(int a[][3])
{
  int m,n,i,j,p,c=0,r=0;
  printf("enter the position and enter p value\n");
  
 do
 { scanf("%d %d %d",&m,&n,&p);
         a[m][n]=p;
         if(p==1)
         {
             c++;
             if(c==3)
             check(a);
         }
         else if(p==2)
         {r++;
         if(r==3)
         check(a);
         }
     }while(m<3&&n<3);
  }
void check(int a[][3])
{
    int i,j,t,s,x=0,y=0,b=0,v=0,w=0;
    static int k;
    //row wise
    for(i=0;i<3;i++)
    {
        for(j=0,t=0,s=0;j<3;j++)
        {
            if(a[i][j]==1)
            t++;
            else if(a[i][j]==2)
            s++;
        }
        if(t==3)
        {
            printf("Zero Wins\n");
         v++;
        break;
        }
        else if(s==3)
        {
            printf("Cross Wins\n");
         w++;
        break;
        }
        else
       b++;
    }
    //column wise
    for(j=0;j<3;j++)
    {
        for(i=0,t=0,s=0;i<3;i++)
        {
            if(a[i][j]==1)
            t++;
            else if(a[i][j]==2)
            s++;
        }
        if(t==3)
        {
            printf("Zero Wins\n");
           v++;
        break;
        }
        else if(s==3)
        {
            printf("Cross Wins\n");
         w++;
        break;
        }
        else
        b++;
    }
    //diagonal wise -1
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {if(i==j)
        {
        if(a[i][j]==1)
        x++;
        else if(a[i][j]==2)
        y++;
        }
        }
        if(x==3)
        {
            printf("Zero Wins\n");
        v++;
        break;}
        else if(y==3)
        {
            printf("Cross Wins\n");
        w++;
        break;}
        else
        b++;
    }
    //diagonal wise -2 
    for(j=2;j>=0;j--)
    {
        for(k=0;k<3;)
        {
        if(a[k][j]==1)
        {x++;
        k++;
        break;}
        else if(a[k][j]==2)
        {
            y++;
           k++;
            break;
        }
        if(x==3)
        {
            printf("Zero Wins\n");
         v++;
        break;
        }
        else if(y==3)
        {
            printf("Cross Wins\n");
         w++;
        break;}
        else
        b++;
    }
}
if(v==1)
printf("Zero Wins\n");
if(w==1)
printf("Cross Wins\n");
if(b==4)
printf("Draw\n");
}



