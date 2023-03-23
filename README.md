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

