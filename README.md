# 2023-03-23
```C

#include <stdio.h>

int main(void)
{
        char code = 'A';
        printf("%d %d %d \n", code, code+1, code +2;) // 65 66 67이 출력된다.
        printf("%c %c %c \n", code, code+1, code +2;) // A B C 가 출력된다.
        return 0;
}
```

```c
#include <stdio.h>

//int main()
{
        double x,y,result;

        printf("두개의 실수를 입력하시오:");
        scanf("%lf %lf",&x,&y);

        result = x + y;
        printf("%f / %f = %f\n", x,y,result);

        result = x - y;
        printf("%f / %f = %f\n", x,y,result);

        result = x * y;
        printf("%f / %f = %f\n", x,y,result);

        result = x / y;
        printf("%f / %f = %f\n", x,y,result);

        return 0;

}
```

```c
#include <stdio.h>

int main(void)
{
    int money, change;
    int price, c5000, c1000, c500, c100;

    printf("물건 값을 입력하시오:");
    scanf("%d", &price); //물건 값을 입력받는다.

    printf("투입한 금액을 입력하시오:");
    scanf("%d", &money);
    change=money-price;

    c1000 = change/1000;
    change = change%1000;

    c500= change/500;
    change = change%500;

    c100 = change/100;
    printf("\n천원권:%d장\n",c1000);
    printf("오백원 동전:%d개\n",c500);
    printf("백원 동전:%d개\n",c100);
    return 0;

}
```
