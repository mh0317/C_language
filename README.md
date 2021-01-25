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





