---
title: "图形化_if_else_if_声明"
date: 2021-11-07T14:20:23+08:00
draft: true
---

# 图形化_if_else_if_声明

## 在写条件语句时，有时候会将 if   if...else if 搞 混，其实 根据 英语语义可以很明确的去理解

<img src="https://blog.clayliu.com/post/img/lang/elseif.png" style="zoom:250%;" />



## C++ 中的 if ... else if

```cpp

#include<iostream>

using namespace std;

int main()
{
    // Declare and initalize variables
    int a = 4;
    int b = 1;

    // if statement
    if (a == 5)
    {
        cout << "Inside if statement (a == " << a << ")" << endl;
    }



    // if and else statement
    // if 后面的表达式 为真 时
    // 执行 if 后 花括号的内容
    // else if 也是
    // 只有 if 和 之后 的 else if 都为假的时候
    // 才执行 else 的 内容

    if(a > 5 )
    {
        cout << "a > 5 (within if else statement)" <<endl;
    }
    else if(b == 10)
    {
        cout << "b == 10 (within else if )" <<endl;
    }
    else{
        cout << " any other case" << endl;
    }


    // switch statement
    switch (a){
        case 4 :
            cout << a << " == 4 (within case 4)" << endl;
            break;
        case 6 :
            cout << a << " == 5 (within case 6)" << endl;
            break;
        default:
            cout << a << " == 5 (within case 6)" << endl;
    }

    return 0;

}
```



## Java 中的 if ... else if

```java
package com.company;
import java.util.Scanner;

public class If_statements {

    public static void main(String[] args) {
        // if  statement = performs a block of code if it's condition evaluates be true
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter your age： ");
        int age = scanner.nextInt();

        if (age >= 25){
            System.out.println("you are " + age + ", you are an adult.");
        }
        else if (age >= 18 ){
            System.out.println("you are " + age + ", BUT go easy ~");
        }
        else {
            System.out.println("you are " + age + ", you can NOT drink.");
        }

    }
}

```

