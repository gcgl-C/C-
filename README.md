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
