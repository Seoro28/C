# C
```c
#include <stdio.h>

void print_stars()
{

    for(int i = 0; i<30, i++;)
        printf("*");
}

int main(void)
{
    print_stars();
    printf("\nHello World!\n");
    print_stars();
    printf("\n");
    return 0;
}
```
```
#define_CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int max(int x, int y)
{
    // return(x>y)? x : y; "한줄로 간결하게!"
    if(x>y)
        return x;

    else 
        return y;
}
int main(void)
{

    int x, y, larger;

        printf("정수 2개를 입력하시오: ");
        scanf("%d,%d", &x,&y)
        larger = max(x,y);
        printf("더 큰 값은 %d입니다. \n", larger);
        return 0;
}
```
