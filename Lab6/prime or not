#include <stdio.h>

int main()

{
   int n,i,flag;
   flag=0;
   printf("Enter a number");
   scanf("%d",&n);
   if(n==0 || n==1){
       flag=0;
       printf("Number is not prime");
   }
   
    for(i=2;i<=n/2;i++){
           if(n%i==0){
               flag=1;
               printf("Number is composite");
               break;
           }
         
       }
    if(flag==0){
        printf("Number is prime");
    }
   
 
    return 0;
}
