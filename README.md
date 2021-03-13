# C-
工程概论C语言小游戏
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
#include <Windows.h>
#include <time.h>
#include <conio.h> /*键盘输入获取*/
 
bool gameOver;
bool stop = false;
bool hit = false;
/*游戏的边框大小*/
const int width = 50;
const int height = 20;
/*蛇的坐标，食物的坐标还有分数*/
int x,y,fruitX,fruitY,score;
/*蛇每个点的坐标*/
int tailX[200],tailY[200];
/*蛇的默认长度*/
int ntail=3;
 
typedef enum
{
        STOP = 0,
        LEFT,
        RIGHT,
        UP,
        DOWN
}Direction;
 
Direction Dir;
/*开始菜单*/
{
    int a;
    printf("------------------------------------------------------------------\n");
    printf("|                              贪吃蛇游戏                        |\n");
    printf("|                              1) 新游戏                         |\n");
    printf("|                              2) 开始边界                       |\n");
    printf("|                              3) 退出游戏                       |\n");
    printf("------------------------------------------------------------------\n");
    printf("---->请输入你的选择:");
    scanf("%d", &a);
}
/*初始化状态*/
void setup()
{
    gameOver = false;
    /*根据当前时间设置“随机数种子”*/
    srand(time(NULL));
    Dir = STOP;
    
    /*贪吃蛇的位置,固定在中间*/
    x= width/2;
    y= height/2;
    /*食物的位置，位置是随机的*/
    fruitX = rand()%width;
    fruitY = rand()%height;
    score = 0;
}
/*绘制界面*/
