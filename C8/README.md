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

//while 문을 이용한 구구단 출력 프로그램

#include <stdio.h>
    int main(void){
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
// 중첩 for 문을 이용하여 *기호를 사각형 모양으로 출력하는 프로그램
#include <stdio.h>

int main(void)
{
    int x,y;

    for(y=0; y<5; y++)
    {
        for(x=0;x <10;x++)
            printf("*");
        printf("\n");
    }

    return 0;
}
```
#include <stdio.h>
int main(void)
{
    int x,y;
    for (y=1; y<=5; y++)
    {
        for(x=0; x<y, x++)
                printf("*");
            printf("\n"); // 내부 반복문이 종료될 때마다 실행
    }

    return 0;
}

// 20번 문제 숫자로 바꾸기 전 기본적인 틀 
```

-항상 c언어 끝나면 그 주안에 해당주차 모든 연습문제,예제 코드 다 쳐보기
-단어, 개념 정리하기 
- 그렇게 찾아서 정리하고 시험은 시험대로 코딩은 코딩대로 실력 늘려보자
처음이라 못할 수 있다.
