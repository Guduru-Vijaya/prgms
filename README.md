#include<stdio.h>
#include<stdlib.h>
struct student
{
    int no;
    char name[10];
    float per;
};
void main()
{
    struct student s[20];
    //struct student *a=(struct student *)malloc(n*sizeof(struct student));
    int i,j,n,pos,ch,ch1,num,sno,temp;
    struct student *a=(struct student *)malloc(n*sizeof(struct student));
    printf("enter n value");
    scanf("%d",&n);
    do
    {
        printf("1.read\n2.print\n3.search\n4.edit\n5.insert\n6.delete\n7.sort as per id\n8.sort as per per\nenter an option\n9.exit \t");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1:for(i=0;i<n;i++)
            {
                printf("enter student no name and per");
                scanf("%d%s%f",&s[i].no,s[i].name,&s[i].per);
            }
            break;
            case 2:for(i=0;i<n;i++)
            {
                printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
            }
            break;
            case 3:printf("enter student no\t");
            scanf("%d",&sno);
            for(i=0;i<n;i++)
            {
                if(s[i].no==sno)
                {
                    printf("student found and the details are\n");
                    printf("%d\t%s\t%f\n",s[i].no,s[i].name,s[i].per);
                }
            }
            if(i==n)
                printf("student not found\n");
            
                break;
            case 4:printf("enter st no");
                scanf("%d",&num);
                printf("what do you want to edit\n1.no\t2.name\t3.per\t");
                scanf("%d",&ch1);
                i=0;
	    while((s[i].no!=num)&&(i<n))
	    {
	       i++;
	    }
                if(ch1==1)
                {
                    printf("number");
                    scanf("%d",&s[i].no);
                }
                else if(ch1==2)
                {
                    
                    printf("name");
                    scanf("%s",s[i].name);
                }
                else
                {
                    
                    printf("per");
                    scanf("%f",&s[i].per);
                }
                printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
                break;
                case 5:
                printf("enter pos");
                scanf("%d",&pos);
                printf("enter new student no,name,per\t");
                scanf("%d%s%f",&s[n+1].no,s[n+1].name,&s[n+1].per);
                for(i=n-1;i>=pos-1;i--)
	            {
		                         s[i+1]=s[i];
		                         s[i]=s[n+1];
	            }
	            n++;
	            for(i=0;i<n;i++)
                {
                      printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
                }
	                     
	           break;
	           case 6:printf("enter student no to delete");
	           scanf("%d",&num);
	           i=0;
	           while((s[i].no!=num)&&(i<n))
	                {
		              i++;
	                }
	             pos=i;
	        for(i=pos+1;i<n;i++)
	         {
		         s[i-1]=s[i];
	         }
	        n--;
	       for(i=0;i<n;i++)
            {
                printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
            }
            break;
            case 7:for(j=0;j<n-1;j++)
            {
                for(i=0;i<n-1;i++)
                {
                    if(s[i].no>s[i+1].no)
                    {
                        a[temp]=s[i];
                        s[i]=s[i+1];
                        s[i+1]=a[temp];
                    }
                }
            }
            for(i=0;i<n;i++)
            {
                printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
            }
            break;
            case 8:for(j=0;j<n-1;j++)
            {
                for(i=0;i<n-1;i++)
                {
                    if(s[i].per>s[i+1].per)
                    {
                        a[temp]=s[i];
                        s[i]=s[i+1];
                        s[i+1]=a[temp];
                    }
                }
            }
            for(i=0;i<n;i++)
            {
                printf("%d\t%s\t\t%f\n",s[i].no,s[i].name,s[i].per);
            }
            break;
            
        }
    }while(ch>0&&ch<9);
}

