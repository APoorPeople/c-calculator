/*#include<stdio.h>
void main()
{
	int numa,numb,d;
	char c;
	printf("input like this 1+1\n");
	scanf("%d,%c,%d",&numa,c,&numb);
	d=numa,c,numb;
	printf("%d\n",d);
}*/
/*#include <stdio.h> 
struct s_node 
{ 
int data; 
struct s_node *next; 
};
typedef struct s_node s_list; 
typedef s_list *link; 
link operator=null; 
link operand=null; 

link push(link stack,int value) 
{ 
link newnode; 

newnode=(link) malloc(sizeof(s_list)); 
if(!newnode) 
{ 
printf("\nMemory allocation failure!!!"); 
return null; 
} 
newnode->data=value; 
newnode->next=stack; 
stack=newnode; 
return stack; 
} 

link pop(link stack,int *value) 
{ 
link top; 
if(stack !=null) 
{ 
top=stack; 
stack=stack->next; 
*value=top->data; 
free(top); 
return stack; 
} 
else 
*value=-1; 
} 

int empty(link stack) 
{ 
if(stack==null) 
return 1; 
else 
return 0; 

} 

int is_operator(char operator) 
{ 
switch (operator) 
{ 
case '+': case '-': case '*': case '/': return 1; 
default:return 0; 
} 
} 

int priority(char operator) 
{ 
switch(operator) 
{ 
case '+': case '-' : return 1; 
case '*': case '/' : return 2; 
default: return 0; 
} 
} 

int two_result(int operator,int operand1,int operand2) 
{ 
switch(operator) 
{ 
case '+':return(operand2+operand1); 
case '-':return(operand2-operand1); 
case '*':return(operand2*operand1); 
case '/':return(operand2/operand1); 
} 
} 

void main() 
{ 
char expression[50]; 
int position=0; 
int op=0; 
int operand1=0; 
int operand2=0; 
int evaluate=0; 

printf("\nPlease input the inorder expression:"); 
gets(expression); 

while(expression[position]!='\0'&&expression[position]!='\n') 
{ 
if(is_operator(expression[position])) 
{ 
if(!empty(operator)) 
while(priority(expression[position])<= priority(operator->data)&& 
!empty(operator)) 
{ 
operand=pop(operand,&operand1); 
operand=pop(operand,&operand2); 
operator=pop(operator,&op); 
operand=push(operand,two_result(op,operand1,operand2)); 
} 
operator=push(operator,expression[position]); 
} 
else 
operand=push(operand,expression[position]-48); 
position++; 
} 
while(!empty(operator)) 
{ 
operator=pop(operator,&op); 
operand=pop(operand,&operand1); 
operand=pop(operand,&operand2); 

operand=push(operand,two_result(op,operand1,operand2)); 
} 
operand=pop(operand,&evaluate); 
printf("The expression [%s] result is '%d' ",expression,evaluate); 
getch(); 
}*/
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
 
int main()
{
int y;
double shu1=0;
double shu2=0;
char fuhao;
 
do
{
  printf("\n         迷你计算器\n\n");
  printf("       1.数据输入\n\n");
  printf("       2.四则运算\n\n");
  printf("       0.退    出\n\n");
  printf("   请选择（0-2）\n");
   
  scanf("%d",&y);
  getchar();
  switch(y)
  {
    case 1: 
            shu1=0;
            shu2=0;
            fuhao=0;
            printf("请输入两个数字，空格分开：");
            scanf("%lf %lf",&shu1,&shu2);
            printf("\n输入完成： %lf   %lf\n",shu1,shu2);
            getchar();
            break;
    case 2: 
            printf("\n请输入运算符号（+ - * /）:");
            scanf("%c",&fuhao);
            getchar();
             
            if(fuhao == '+')
                printf("\n加法，运算结果：%lf\n",shu1+shu2);
            if(fuhao == '-')
                printf("\n减法，运算结果：%lf\n",shu1-shu2);
            if(fuhao == '*')
                printf("\n乘法，运算结果：%lf\n",shu1*shu2);
            if(fuhao == '/')
                printf("\n除法，运算结果：%lf\n",shu1/shu2);
         
            break;
    case 0:
            printf("    谢谢使用\n");
            exit(1);
    default:
            printf("    输入错误,请重新输入\n");
  }
}
while (y>0);
}
