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

