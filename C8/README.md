```C
//반복문 예제
#include <stdio.h>
int main(void)
{
    int i = 0;

    while(i < 5)
    {
        printf("Hello World\n");
        i++;
    } 
    
    return 0;
} 

//Hello world가 0 1 2 3 4 총 다섯 번이 출력됨

```
// while 문을 이용한 구구단 출력 프로그램
#include <stdio.h>
int main(void)
{
    int n;
    int i = 1;

    printf("출력하고 싶은 단: ");
    scanf("%d", &n);
    while (i <= 9)
{
    printf("%d*%d = %d \n", n, i, n*i);
    i++;
}
    return 0; 
}
```
// 정수를 입력받아 1부터 입력받은 정수까지의 짝수 합을 구하는 식
#include <stdio.h>
int main(void)
{
    int i, n, sum; // 변수 선언

    printf("정수를 입력하시오:"); // 입력 안내 메시지 출력
    scanf("%d", &n); // 정수값 입력

    i = 1; // 변수 초기화
    sum = 0;

    while(i <= n)
    {
    sum += i; // sum = sum + i;와 같다.
    i = i + 2;
    }
    printf("1부터 %d까지의 짝수합은 %d입니다\n", n, sum);
    return 0;
}
```
