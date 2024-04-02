---
title: C++爱心代码
date: 2023-11-14 20:12:52
tags:
  - c++
categories:
  - 编程学习
mathjax: true
---
## C++实现爱心代码
### 前言
兴趣是最好的老师，实践是最好的考试，学完基础知识就可以找一些简单的代码玩玩。画一个爱心代码送给自己喜欢的人（虽然作者单身），谁说理工男不懂浪漫（QAQ）
### 爱心曲线方程

$$
x^2+(5y/4-\sqrt[2]{|x|} )=1
$$

### 代码实现

~~~c++
#include<iostream>
#include<cmath>
using namespace std;

int main()
{
    for(float y=1.3;y>=-1.1;y-=0.06){
           
        for(float x=-1.1;x<=1.1;x+=0.025)
        {
            if(x*x+pow(5.0*y/4.0-sqrt(fabs(x)),2)-1<=0)
            {
                cout<<'*';
            }
            else
                cout<<' ';
        }
        cout<<endl;
    }
    system("pause");
    return 0;

}
~~~
### 输出形状
[![piY9XM6.png](https://z1.ax1x.com/2023/11/14/piY9XM6.png)](https://imgse.com/i/piY9XM6)