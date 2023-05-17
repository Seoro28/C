```c


// Example 01 동전 던지기 게임 

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

int coin_toss(void);

int main(void)
{
    int toss;
    int heads = 0;
    int tails = 0;                  
    srand((unsigned)time(NULL));    /*srand : 프로그램 실행시마다 난수 생성기의 시드값을 초기화해줌.
                                    이렇게 지정하는 이유는 한번 결정된 난수가 계속 같은 난수 값을 발생시키기 때문에
                                     매번 난수를 다르게 생성하도록 설정한 것이다. */

    for(toss = 0; toss < 100; toss++){
        if(coin_toss() == 1)
            heads++;
        else
            tails++;
    }
    printf("동전의 앞면: %d \n", heads);
    printf("동전의 뒷면: %d \n", tails);
    return 0;
}

int coin_toss(void){
    int head = rand() % 2;              // 0 또는 1 값을 반환하여 동전 던지기(앞,뒷면) 결과를 나타냄.
    return head;
}

/*이 코드에서 알 수 있듯이 for문을 이용해 앞면 뒷면을 참, 거짓으로 나누고
그 횟수를 난수로 만들어내는 함수(rand와 srand)를 이용해 적용시켜봄으로써 이해에 도움이 되었던 예제임.*/


```c


// Example 02 자동차 게임(난수를 이용한!!)
/* 알고리즘
 1. 난수 발생기를 초기화한다
 2. for(i=0; i<주행시간; i++)
 3. 난수를 발생하여서 자동차1의 주행거리에 누적한다.
 4. 난수를 발생하여서 자동차2의 주행거리에 누적한다.
 5. disp_car()를 호출하여서 자동차1을 화면에 *표로 그린다.
 6. disp_car()를 호출하여서 자동차2를 화면에 *표로 그린다.
*/
#include <stdlib.h>
#include <stdio.h>
#include <conio.h>      // getch함수 : 사용자에게 키보드로 하나의 키를 입력받는 함수 -> 이것을 사용하려고 선언하는 것
#include <time.h>

void disp_car(int car_number, int distance)
{
    int i;
    printf("CAR #%d:", car_number);
    for(i = 0; i< distance/10; i++){
        printf("*");
    }
    printf("\n");
}

int main(void){
    int i; 
    int car1_dist=0, car2_dist=0;

    srand((unsigned)time(NULL)); // 앞전에 동전던지기에서와 마찬가지로 난수 생성 초기화를 위함!!

    for(i=0; i<6; i++){
        car1_dist += rand()% 100;
        car2_dist += rand()% 100;
        disp_car(1,car1_dist);
        disp_car(2,car2_dist);
        printf("---------------------\n");
        _getch();
    }
    return 0;
}

/* 자동차 2대가 경주하는 게임을 구현한 것이고, 각 자동차는 랜덤한 수를 받아
별(*)표시로 거리를 나타냄.
'disp_car' 함수가 자동차 번호, 주행 거리를 입력받아 해당번호의 자동차의 거리를 표현해주고
'main'함수 에서는 난수 생성기를 초기화 하여 반복문을 통해 자동차 거리를 누적시킴.
'_getch'함수를 사용하여 입력을 기다림.
 이것을 총 6번 반복하여 자동차 경주를 끝마침.
*/


```c


/* Example 03 자동차를 3대로 늘려보자
예상 : 3번째 차량만 추가하면 될 것 같음.

   1. int main 함수에  int car3_dist= 0; 추가
   2. for 문 안에 
     car3_dist += rand()% 100;
     disp_car(3,car3_dist);
*/

#include <stdlib.h>
#include <stdio.h>
#include <conio.h>  
#include <time.h>

void disp_car(int car_number, int distance)
{
    int i;
    printf("CAR #%d:", car_number);
    for(i = 0; i< distance/10; i++){
        printf("*");
    }
    printf("\n");
}

int main(void){
    int i; 
    int car1_dist=0, car2_dist=0, car3_dist=0;

    srand((unsigned)time(NULL)); 

    for(i=0; i<6; i++){
        car1_dist += rand()% 100;
        car2_dist += rand()% 100;
        car3_dist += rand()% 100;
        disp_car(1,car1_dist);
        disp_car(2,car2_dist);
        disp_car(3,car3_dist);

        printf("---------------------\n");
        _getch();
    }
    return 0;
}
/* 처음에 3번 안나와서 코드 잘못친 줄 알았음....
   예상했던 것처럼 자동차 한개 추가하면 해결이 가능했음!!
CAR #1:******
CAR #2:*******
CAR #3:
---------------------
CAR #1:***************
CAR #2:**************
CAR #3:*********
---------------------
CAR #1:************************
CAR #2:*******************
CAR #3:******************
---------------------
CAR #1:**************************
CAR #2:***********************
CAR #3:***************************
---------------------
CAR #1:***************************
CAR #2:*************************
CAR #3:*****************************
---------------------
CAR #1:*********************************
CAR #2:********************************
CAR #3:********************************
---------------------
PS C:\20234403_A> */


```c


/* floor()함수와 ceil()함수

    double result, value = 1.6;

    result = floor(value);
    printf("%lf", result);

    -> result는 1.0 이 된다

    result = ceil(value);
    printf("%lf", result);

    -> result는 2.0이다

    floor 함수는 정수 이외의 부분은 버리고 출력 값을 가진다.
    ceil 함수는 정수에 소수부분을 올림하여 출력 값을 가진다.
*/


/* fabs() 함수
    이 함수는 실수를 받아 절대값을 반환한다.

    printf("12.0의 절대값은 %f\n", fabs(12.0));
    printf("12.0의 절대값은 %f\n", fabs(-12.0));

    출력값은 이렇게 받게 된다.

    12.0의 절대값은 12.000000
    12.0의 절대값은 12.000000

*/


/* pow() 함수와 sqrt() 함수
    이 두 함수는 제곱,제곱근과 연관된 함수들이다.

    pow()함수는 제곱 연산을 수행하는 함수이다.
    sqrt()함수는 제곱근 연산을 수행하는 함수이다.

    예를들어
    printf("10의 3승은 %.0f.\n", pow(10.0, 3.0)); 
    printf("16의 제곱근은 %.0f.\n", sqrt(64));

    10의 3승은 1000.
    16의 제곱근은 4. 로 값을 받는다.
*/


```c


// Example 04 삼각함수 라이브러리
#include <math.h>   //여러가지 수학 함수들을 포함하는 표준 라이브러리
#include <stdio.h>

int main(){
    double pi = 3.1415926535;
    double x,y;

    x = pi /2 ;
    y = sin(x);
    printf("sin( %f ) = %f\n", x,y);
    y = cos(x);
    printf("cos(%f) = %f\n", x,y);
}

/* 이에 대한 출력값이다.
    sin( 1.570796 ) = 1.000000
    cos(1.570796) = 0.000000

    위 코드는 사인값과 코사인값을 계산하고 출력하는 식이며
    90도에서의 사인값과 코사인값을 출력한다.
*/


/* 중간 점검
    Q. 90도에서의 사인 값을 계산하는 문장을 작성해보시오.

    A.

    순서는 다음과 같다.
    1. 각도(90도)를 설정한다
    2. 라디안 변환 angle(90도) * (PI / 180) 과정을 거친다 
    3. 사인값 sin(radians) 을 계산한다 


    #include <stdio.h>
    #include <math.h>

    #define PI 3.14159265

    int main() {
    double angle = 90;  // 각도 설정
    double radians = angle * (PI / 180);  // 라디안으로 변환 : 파이는 180도
    double sinValue = sin(radians);  // 사인 값 계산

    printf("90도에서의 사인 값: %lf\n", sinValue);

    return 0;
}

    출력값은 sin 90 즉 1이 출력된다.


    Q. rand( ) % 10 이 계산하는 값의 범위는?

    A. 0 ~ 9까지의 범위 내에서 값을 계산한다.

*/


```c


// Example 05

#include <stdlib.h>
#include <stdio.h>

int main(void){

    system("dir");  // 시스템 명령어 "dir"을 실행하여 현재 디렉터리의 내용을 출력
    printf("아무 키나 치세요\n"); 
    _getch();       // 사용자의 키 입력을 기다림
    system("cls");  // 시스템 명령어 "cls"를 실행하여 화면을 지움

    return 0;
}

/* 즉 이 코드는 디렉터리 내용을 출력하고 사용자의 키입력을 할때까지 기다렸다가
화면을 지우도록 만들어졌음.*/


/* 출력 값은   
 Volume in drive C has no label.
 Volume Serial Number is 14C0-D5D7

 Directory of C:\20234403_A

2023-05-17  오전 11:05    <DIR>          .
2023-05-17  오전 11:05    <DIR>          ..
IR>          .vscode
32_Ac
 */


```c


/* Example 06 시간 맞추기 게임
    사용자에게 정확한 시간을 예측하게 하는 게임을 만들어보려고 한다.
    사용자에게 10초가 지나면 엔터키를 입력하라고 한 후
    정확한 시간과 얼마나 차이가 나는지를 출력한다.
*/

#include <stdio.h>
#include <time.h>

int main(){
    time_t start, end;  // time_t는 unsigned long과 동일하다.
    start = time(NULL);
    printf("10초가 되면 아무 키나 누르세요\n");
    while (1)
        {
            if (getchar())
                break;
        }
    printf("종료되었습니다.\n");
    end = time(NULL);
    printf("경과된 시간은 %ld 초입니다. \n", end - start);
    return 0;

}

/*
위의 코드는 프로그램이 실행되는 동안 경과된 시간을 측정하는 코드이다.
'start'에 현재 시간을 저장하기 위해 'time(NULL)' 함수를 호출하고
사용자에게 "10초가 되면 아무 키나 누르세요" 를 출력
사용자가 키를 입력하면 문구를 출력하고 루프를 종료함.
'end' 함수에 시간을 경과된 시간을 계산하고 이를 출력함.
*/

  
```c
  
  
/* Example 07 나무 높이 측정 
    각도기와 삼각 함수를 이용하면 나무의 높이를 측정할 수 있다.
    다음 그림을 참조하여서 나무의 높이를 측정하는 프로그램을 작성하여보자.
*/



#define _CRT_SECURE_NO_WARNINGS
#include <math.h>
#include <stdio.h>

int main(void){
    double height, distance, tree_height, degrees, radians;

    printf("나무와의 길이(단위는 미터): ");
    scanf("%lf", &distance);
    
    printf("측정자의 키(단위는 미터):");
    scanf("%lf", &height);

    printf("각도(단위는 도):");
    scanf("%lf", &degrees);

    radians = degrees * (3.141592 / 180.0);

    tree_height = tan(radians) * distance + height;
    printf("나무의 높이는(단위는 미터): %lf \n", tree_height);

    return 0;

}
/* 사용자로부터 나무와의 거리, 측정자의 키, 각도를 입력받아 트리의 높이를 측정하고 
    출력하는 코드이다.
    1. height, distance, tree_height, degrees, radians 의 변수 선언
    2. 사용자로부터 나무와의 거리를 입력받고 'distance'에 저장
    3. 측정자의 키와 각도를 입력받고 각각 'height','degrees' 에 저장
    4. 입력된 각도를 라디안으로 변환하기 위해 'radians'에 저장
    5. 'tan' 함수를 사용하여 탄젠트 값 계산, 이 값을 'tree_height'에 저장하고 출력한다
*/


```c


// Example 08 삼각함수 그리기


#include <stdio.h>
#include <math.h>
#define PI 3.141592

double rad(double degree){
    return PI * degree / 180.0;
}

void drawbar(int height){
    for (int i = 0; i < height; i++)
        printf("*");
    printf("\n");
}

int main(void){
    int degree, x, y;
    for(degree = 0; degree <=90; degree += 10){
        y = (int)(60 * sin(rad((double)degree)) + 0.5);
        drawbar(y);
    }
    return 0;
}

/* 출력값을 보면 싸인함수 막대그래프를 옆으로 회전시킨 모양으로 나온다.
    삼각함수를 계산하는 라이브러리 함수를 이용하였고 각각의 각도에 대한
    막대 그래프가 별표로 출력된다.
*/


```c


// Example 09 Mini project : 공학용 계산기 프로그램 작성

#include <stdio.h>
#include <math.h>

int menu(void){
    int n;
    printf("1. 팩토리얼\n");
    printf("2. 싸인\n");
    printf("3. 로그(base 10)\n");
    printf("4. 제곱근\n");
    printf("5. 순열(nPr)\n");
    printf("6. 조합(nCr)\n");
    printf("7. 종료\n");
    printf("선택해주세요: \n");
    scanf("%d", &n);
    return n;
}

void factorial(){
    
    long long n, result = 1, i;
    printf("정수를 입력하시오: ");
    scanf("%lld", &n);
    for(i = 1; i <= n; i++)
        result = result * i;
    printf("결과 = %lld\n\n", result);
}

void sine(){

    double a, result;
    printf("각도를 입력하시오: ");
    scanf("%lf", &a);
    result = sin(a);
    printf("결과 = %lf\n\n", result);
}

void logBase10(){

    double a, result;
    printf("실수 값을 입력하시오 : ");
    scanf("%lf", &a);
    if (a<= 0.0)
        printf("오류\n");
    else
        result = log10(a);
        printf("결과 = %lf\n\n", result);
}

int main(void){

    while(1){
        switch (menu()){
            case 1 : 
                factorial();
                break;
            case 2 :
                sine();
                break;
            case 3 :
                logBase10();
                break;
            case 7 :
                printf("종료합니다.\n");
                return 0;
            default :
                printf("잘못된 선택입니다.\n");
                break;

        }
    }
}

/*  1.'menu' 함수를 통해 사용자로 부터 입력을 받음. 
    2. 선택한 메뉴에 따라 프로그램 실행 (팩토리얼, 싸인, 로그, 나머지는 채워야함)
    3. 그리고 while문을 통해 실행 후 빠져나온다.
    이 프로그램은 어떠한 연산을 선택했을 때 그 연산의 값을 계산해주고 결과 값을 출력해준다.
*/


```c
