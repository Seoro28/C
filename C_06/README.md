```c
#include <stdio.h>

int main(){
    int n,i=1,sum=0;
    
    printf("정수를 입력하시오: ");
    scanf("%d", &n);

    while (i<=n)
    {
        if(i%2==0)
        {
            sum += i;
        }

        i++;
        }
    printf("1부터 %d까지의  짝수의 합은 %d입니다",n, sum);

    return 0;  

}
```
#include <stdio.h>

int main(void)
{
    int i,n,sum;

    i=0;
    sum = 0;
    while(i<5)
    {
        printf("값을 입력하시오: ");   
        scanf("%d", &n);
        sum = sum +n;
        i++;
    }
    printf("합계를 %d입니다.\n",sum);

    return 0;

}
```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main(void)
{
    int number,sum = 0;

    do{

        printf("정수를 입력하시오:");
        scanf("%d",&number);
        sum += number;

    } while(number != 0);

    printf("숫자들의 합 = %d\n", sum);

    return 0;

}
```
# include <stdio.h>

int main(void)
{
    int i = 0;
    do
    {
        printf("1---새로만들기\n");
        printf("2---파일열기\n");
        printf("3---파일닫기\n");
        printf("하나를 선택하시오.\n");
        scanaf("%d",&i);


        /* code */
    } while (i<1||i>3);

    printf("선택된 메뉴=%d\n",i);
    return 0;
    



}
```
#include <stdio.h>
#include <stdlib.h>

int main(void){
    srand((unsigned)time(NULL));
    int answer = rand()%100;
    int guess;
    int tries = 0;
    
    do{
        printf("정답을 추측하여 보시오: ");
        scanf("%d",&guess);
        tries++;

    if(guess>answer)
            printf("HIGH\n");
        if(guess<answer)
            printf("LOW\n");
    }while(guess != answer);

    printf("축하합니다. 시도횟수=%d\n", tries);
    return 0;

}
```
#include <stdio.h>

int main() {
    int n;
        scanf("%d", &n);


        for(int i = 1; i<= n; i++)
    {
            for(int j = 1; j<= n-i; j++){
            printf(" ");}
            for(int j=1; j <= i; j++){
        printf("*");} 
        printf("/n");
    }
    return 0;

}
```
