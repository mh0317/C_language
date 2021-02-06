# C_language

  21-01-24
------------------------
#include<stdio.h>

int main(void)
{
    printf("Hello world!\n");
}
========================


21-01-25
-------------------------
#include<stdio.h>

int main(void)
{
  printf("강한친구 대한육군\n");
  printf("강한친구 대한육군\n");
}

==========================

#include<stdio.h>

int main(void)
{
  for(int i=0; i<2; i++)
  {
    printf("강한친구 대한육군\n");
  }
}
=============================
//성적을 입력하고 성적의 평균 값 도출하기 cs50 샌드박스이용이 필수...
#include<stdio.h>
#include<cs50.h>

float average(int length, int array[]);
//실수체계의 평균이라는 변수를 선언

int main(void)
{
  int n = get_int("과목 수 : ");
  //과목 수를 입력 받아 n을 결정
  
  int scores[n];
  for (int i = 0 ; i < n ; i++)
    {
      scores[i]=get_int("Scores%i is ",i+1); // i가 0부터 시작해서 보기 좋게 +1을 하여 1부터 시작하게 만듦
    }
   printf("성적의 평균 점수는 %.1f 입니다.\n",average(n,scores)); 
}

float average(int length, int array[])
{
  int sum = 0;
  for (int j = 0; j < length; j++)
    {
        sum +=array[j]; //sum = sum + array[j];
    }
    return sum/(float)length;
}

---------------------------------
//성적을 입력하고 성적의 평균 값 도출하기 c나c++에서도 정상 가 
#include<stdio.h>

int sum = 0;동 
float average(int length, int array[]);
//실수체계의 평균이라는 변수를 선언

int main(void)
{
  int n;
  //int n = get_int("과목수 : ");
  printf("입력할 과목 수: ");
  scanf("%i",&n); 
  //과목 수를 입력 받아 n을 결정
  
  int scores[n];
  for (int i = 0 ; i < n ; i++)
    {
      //scores[i]=get_int("Scores%i is ",i+1); // i가 0부터 시작해서 보기 좋게 +1을 하여 1부터 시작하게 만듦
    	printf("Score%i is ",i+1);
		scanf("%i",&scores[i]); 
	}
   printf("%i 과목의  평균 점수는 %.1f 입니다.\n",n,average(n,scores));
   printf("%i 과목의  총 점수는 %i 입니다.\n",n,sum); 
}

float average(int length, int array[])
{
  for (int j = 0; j < length; j++)
    {
        sum +=array[j]; //sum = sum + array[j];
    }
    return sum/(float)length;
}
======================================
1/27
// 단위변환 예제 
#include <stdio.h>

int main(void)
{
	printf("********************1번 문제********************\n");
	int n;
	printf("천만 이하의 한 수를 입력하시오 : ");
	scanf("%d",&n);
	printf("즉 입력이 %d 이면 %d 만 %d 천 %d 백 %d 십 %d 입니다.\n",\
	n, n/10000, n%10000/1000, n%10000%1000/100, n%10000%1000%100/10, n%10000%1000%100%10/1);
	

}
1/28
//while문을 통한 학점 확인 코드 
#include<stdio.h>


const int N = 9; 
const char* grade[N]={"A+","A","B+","B","C+","C","D+","D","F"};
const int score[N]={95,90,85,80,75,70,65,60,0};

int main(void)
{
  printf("_______________________________________________________________________________\n");
  printf("|학점 프로그램                                                                 |\n");
  printf("|종료를 원하면 '999' 를 입력하세요                                             |\n");
  printf("|______________________________________________________________________________|\n");
  printf("|                                [학점 테이블]                                 |\n");
  printf("|점수 컷 : 95     90      85      80      75      70      65      60      0    |\n");
  printf("|학점 컷 : A+     A       B+      B       C+      C       D+      D       F    |\n");
  printf("|______________________________________________________________________________|\n");



  while(1)
  {
	int input_score = 0;
	
    printf("성적을 입력하세요 (0~100) : ");
    scanf("%i",&input_score);

	if(input_score == 999){
    	printf("학점 프로그램을 종료합니다.\n");
    	break;  
  	}
    
    if(input_score < 0 || input_score > 100){
		printf("성적을 올바르게 입력하세요~! (0 ~ 100)\n");
		continue;
	}
		
    for(int i = 0; i < N;i++)
		{if (input_score >= score[i]){
      		printf("입력하신 성적은 %i 이고, 학점은 %s 입니다.\n",input_score,grade[i]);
      		break;		
					
			}
		}

  	}	
    

}

//do while문을 통한 성적에 대한 학점확인 코 드 
#include<stdio.h>
#define N 9


const char *grade[N] = {"A+", "A", "B+", "B", "C+", "C", "D+", "D", "F"};
const int score[N]={95,90,85,80,75,70,65,60,0};
int input_score = 0;

int main(void)
{
  printf("_______________________________________________________________________________\n");
  printf("|학점 프로그램                                                                 |\n");
  printf("|종료를 원하면 '999' 를 입력하세요                                             |\n");
  printf("|______________________________________________________________________________|\n");
  printf("|                                [학점 테이블]                                 |\n");
  printf("|점수 컷 : 95     90      85      80      75      70      65      60      0    |\n");
  printf("|학점 컷 : A+     A       B+      B       C+      C       D+      D       F    |\n");
  printf("|______________________________________________________________________________|\n");


do{
    
    printf("성적을 입력하세요 (0~100) : ");
    scanf("%i",&input_score);
    
    
    if(input_score > 100 || input_score < 0 ){
		printf("성적을 올바르게 입력하세요~! (0 ~ 100)\n");
		continue;
	}
		
    for(int i =0; i < N;i++)
		{if (input_score >= score[i]){
      				printf("입력하신 성적은 %i 이고, 학점은 %s 입니다.\n",input_score,grade[i]);
      		break;						
			}
		}
	}     
  while(input_score != 999);
    printf("학점 프로그램을 종료합니다.\n");

}

=====================================
1/29
// 원하는 값을 입력하여 결과 값 얻기   

#include <stdio.h>

int main(void)
{
	printf("******************************************\n"); 
	const double pi = 3.141592;
	double r;
	printf("구의 반지름을 입력하시오 : ");
	scanf("%lf",&r);
	printf("구의 반지름은 %.1lf입니다\n",r);
	printf("표면적은 %.6lf입니다.\n",4*pi*r*r);
	printf("체적은  %.6lf입니다.\n",4*pi*r*r*r/3);
		
	return 0; 
}
====================================
// 1/31 C programming 18~60p

#include<stdio.h>

int main()
{
	//문자 상수 사용하기 
	printf("%c\n",'a'); 		// 문자 상수 'a' 출력
	printf("%c\n",97);  		// ASCII 코드 값이 97인 문자 출력
	printf("%c\n",'\141');	 	// ASCII 코드 값이 8진수('\') 141인 문자 출력 
	printf("%c\n",'\x61'); 		// ASCII 코드 값이 16진수('\x') 61인 문자 출력
	
	printf("삐음 : %c\n",'\a'); 			// 이스케이프 문자 삐음을 출력
	printf("단일 인용부호 : %c\n",'\''); 	// 이스케이프 문자 '를 출력 
	printf("abcdef\b\b\b\b\n");				// 이스케이프 문자 백스페이스를 출력 ab 
	printf("%s\n","ghijk");					// 문자열 상수 출력 ghijk
	
	//정수형 상수 사용하기 
	printf("%d %d\n",sizeof 2013, sizeof 2013L); // 2013이 차지하는 사이즈는 4 와 4이다. 
	printf("%d %d %d\n",2013, 03735,0x7dd);      // 10진법, 8진법, 16진법인 값을 10진법으로 표현 
	printf("%d %o %x\n",2013,2013,2013); 		 // 2013을 10진법, 8진법, 16진법으로 표현 
	printf("%d %d\n",2147483648,2147483648L); 	 // 32비트로 표현가능한 최대값을 벗어나서 다른 값이 뜸 
	printf("%u\n",2147483648);					 // %u는 부호 비트를 별도로 고려하지 않는다. 따라서 위와 달리 정상 출력 
	
	//실수형 상수 사용하기
	printf("%d %d\n",sizeof 3.14f, sizeof 3.14);		// 3.14f의 데이터 크기는 4byte ,3.14의 데이터 크기는 8byte
	printf("%lf %lf\n",0.314e1,31.4e-1);				// %lf는 소수점 아래 6자리까지 표현	
	printf("%lf\n",0.123456789012345678901); 			// %lf으로 출력가능한 범위를 알수있다. => 6자리 표현 
	printf("%.20lf\n",0.123456789012345678901);			// %lf 면서 소수점 아래 20자리 출력 => 20자리 중 부족한 자리는 0으로 채워 출력 
	printf("%.20f\n",0.12345678901234567890f);			// %f면서 소수점 아래 20자리 출력 => f여서 6자리이후 비정확하게 출력 
	
	return 0; 
	
}

// 2월 1일

#include<stdio.h>

int main(void)
{
	//변수 선언
	int a1, a2, a3;
	
	a1 = 10;
	a2 = 20;
	a3 = a1 + a2;
	
	printf("a1 = %d, a2 = %d, a3 = %d\n",a1,a2,a3); 	// 10 , 20 , 30
	
	a3 = a2 / 2 ;
	
	printf("a1 = %d, a2 = %d, a3 = %d\n",a1,a2,a3);		//10 , 20 , 10
	
	
	//정수형 변수의 사용
	unsigned char age = 97;
	int max = 2147483647; 							//int의 최대치 값을 max라는 변수에 저장 
	int max_plus_1 = max + 1;						//int 타입의 Max plus 1에  max + 1 라는 값을 저장 but 범위 벗어나서 넣은 값과 다른 값 출력 
	unsigned int super = max + 1;					//int 타입이나, 부호가 없어서 범위가 2배 증가하여 원하는 결과값 정상 출 력 
	
	printf("age = %d\nmax = %d\n",age,max);
	printf("max + 1 = %d\n",max_plus_1);
	printf("super = max + 1 = %u\n",super); 
	
	//실수형 변수의 사용
	float radius = 10.0;
	float area;
	area = 3.14f * radius * radius;					// const나 define으로 Pi를 정의 내리고 사용해도 좋을듯 불변값이니 
	
	printf("반지름이 %f인 원의 넓이는 %f 입니다.\n",radius,area); 
	
	//변수와 자료형 실습
	//Q1 밑변이 3cm , 높이가 5cm인 삼각형의 넓이는?
	float base = 3;
	float height = 5;
	float Tri_area;
	
	Tri_area = 0.5 * base * height;
	
	printf("밑변 %fcm, 높이 %fcm의 삼각형의 넓이는 %f cm^2 입니다.\n",base,height,Tri_area);  // %d로 할 경우 이상한 결과값이 출력된다. 
	
		//Q2 화씨 온도를 섭씨온도로 변환하는 프로그램
	float fahrenheit,celsius;
	
	fahrenheit = 72.0; 
	celsius    = (5.0/9.0) * (fahrenheit - 32);
	
	printf("화씨온도 %f도는 섭씨온도 %f도입니다. \n",fahrenheit,celsius);
	
	return 0;  
	
	
	
	 
 } 
 
 
 // 애너그렘(anagram) 판별 
#include<stdio.h>
#include<string.h>
/*
입력값: 12345, 54321 -> 출력값: True
입력값: 14258, 25431 -> 출력값: False
입력값: 11132, 21131 -> 출력값: True
*/
int IsAnagram(const char*s1, const char*s2);
void TestIsAnagram(const char*s1, const char*s2);

int main()
{
 	TestIsAnagram("mother","therom");
	TestIsAnagram("12345","54321");
	TestIsAnagram("14258","25431");
	TestIsAnagram("11132","21131");
	TestIsAnagram("cheese","eseche");
	return 0; 
 }


void TestIsAnagram(const char*s1, const char*s2)
{
	printf("====Test : %s vs %s====\n",s1,s2);
	if(IsAnagram(s1,s2))
	{	
		printf("Anagram Result : True\n");
	}
	else
		printf("Anagram Result : False\n");
 }
 
   

int IsAnagram(const char *s1, const char *s2)
{
    int i ,j;
    for(i=0;s1[i];i++)//s1[i] 문자가 참이면(거짓은 종료 문자임) 반복
    {
        for(j=0;s2[j];j++)//s2[j] 문자가 참이면(거짓은 종료 문자임) 반복
        {
            if(s1[i] == s2[j])//s1[i]와 s2[j]가 같으면
            {
                break;//반복문 탈출(s2[j]은 참인 상태임)
            }           
        }
        if(s2[j]==0)//s2[j] 문자가 거짓이면(같은 문자가 없을 때)
        {
            return 0;//anagram이 아님
        }
    }
    return 1;//anagram임

} 

#include<stdio.h>
#include<string.h>
void S_D(int arr[],int length) // Shortest Distance : 최단거리
{
if(length % 2 == 0) // 배열 길이가 짝수인 경우
{
int avg = (arr[length/2-1]+arr[length/2])/2;   //배열길이 짝수면 ,arr[1], arr[2]만고려하면됨.
printf("출력값 : %d\n",avg);
}
else
{ // 배열 길이가 홀수인 경우
int avg = arr[length/2];    //홀수면 딱! 중간을 고려해야지.
printf("출력값 : %d\n",avg);
}
}
void print(int arr[],int length)
{ // 입력돼있는 배열 출력 함수
printf("입력값 :");
for(int i=0;i<length;i++)
printf("%2d",arr[i]);
printf(" -> ");
}
int main()
{
int arr[] = {2,2,2,4};
int length = sizeof(arr)/sizeof(int); // arr의 길이 계산
print(arr,length); // 배열 출력
S_D(arr,length); // 최단거리 출력
int arr2[] = {1,2,3,4,5};
int length2 = sizeof(arr2)/sizeof(int); // arr2의 길이 계산 (<- 4*5 / 4 = 5)
print(arr2,length2); // 배열 출력
S_D(arr2,length2); // 최단거리 출력
return 0;
}

===============================================
#include <stdio.h>

int main(void)
{
    char *s = "EMMA";
    printf("%s\n", s);      // 문자 EMMA가 출력
    printf("%p\n", s);      // 문자 EMMA가 저장된 주소(포인트)가 출력 0x42aeca
    printf("%p\n", &s);     // 문자 EMMA가 저장된 주소(포인트)의 주소가 출력?! 0x7fff1ba54660
    printf("%p\n", &s[0]);  // 문자 E가 저장된 주소가 출력 0x42aeca
    printf("%p\n", &s[1]);  // 문자 2번째 글자인 M이 저장된 주소가 출력 0x42aecb
    printf("%p\n", &s[2]);  // 문자 3번째 글자인 M이 저장된 주소가 출력 0x42aecc                   
}
// 배열명 arr == 배열의 시작 주소 == 첫 원소의 시작 주소 &arr[0]







