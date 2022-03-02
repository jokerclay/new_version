---
title: "【C】什么是typedef"
date: 2021-11-16T13:11:31+08:00
draft: true
---

# 【C】什么是typedef

# 什么是 typedef ?

## `typedef` is a keyword  used in C language to assign alternative names to existing datatypes . Its mostly used with user defined datatypes, when names of the datatypes become slightly complicated to use in programs.

## typedef 是 C 语言中的关键字，给 现有的 数据类型 自定义一个名字， 通常用于用户自定义数据类型，

## 当 程序的数据类型变得复杂的时候，可以使 code  更简洁

```c
#include <stdio.h>
#include <stdlib.h>


// you can give it another name to a datatype
// your code define your own datatype name
//
// Example:

typedef struct Point{
    double x,y;

} Point;
// 或者
typedef struct Point Point

int main(int argc, char *argv){
    Point p;
    p.x = 1.2;
    p.y = 6.35;

    printf("%lf %lf \n", p.x, p.y);

    return 0;
}
```



## 如果将 typedef 和 花括号最后 的 point 去掉： 如下

```c
#include <stdio.h>
#include <stdlib.h>


// you can give it another name to a datatype
// your code define your own datatype name
//
// Example:

struct Point{
    double x,y;

};

int main(int argc, char *argv){
    Point p;
    p.x = 1.2;
    p.y = 6.35;

    printf("%lf %lf \n", p.x, p.y);

    return 0;
}
```

## 会报错

```
 gcc -o typedef typedef.c
typedef.c: In function ‘main’:
typedef.c:16:5: error: unknown type name ‘Point’; use ‘struct’ keyword to refer to the type
   16 |     Point p;
      |     ^~~~~
      |     struct
typedef.c:17:6: error: request for member ‘x’ in something not a structure or union
   17 |     p.x = 1.2;
      |      ^
typedef.c:18:6: error: request for member ‘y’ in something not a structure or union
   18 |     p.y = 6.35;
      |      ^
typedef.c:20:27: error: request for member ‘x’ in something not a structure or union
   20 |     printf("%lf %lf \n", p.x, p.y);
      |                           ^
typedef.c:20:32: error: request for member ‘y’ in something not a structure or union
   20 |     printf("%lf %lf \n", p.x, p.y);
      |                                ^

```



# 报错原因：

## 在 `main` 函数中， 没有 typedef  Point ， 编译器不认识 Point 这个数据类型

## Option 1 :

## 使用 typedef 

## Option 2:

## 在 Point 前面 加  struct  ,告诉编译器 Point 是个 struct

```c
#include <stdio.h>
#include <stdlib.h>


// you can give it another name to a datatype
// your code define your own datatype name
//
// Example:

struct Point{
    double x,y;

};

int main(int argc, char *argv){
    struct Point p;
    p.x = 1.2;
    p.y = 6.35;

    printf("%lf %lf \n", p.x, p.y);

    return 0;
}
```

 

















