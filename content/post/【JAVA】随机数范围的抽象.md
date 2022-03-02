---
title: "【JAVA】随机数范围的抽象"
date: 2021-11-07T13:35:01+08:00
draft: true
---

# 将 JAVA 的 Random 范围抽象出来，从而只用考虑随机数的 开始点 和 结束点



```java
package com.company;
// 导入 Random 类
import  java.util.Random;

public class Random_numbers {

    public static void main(String[] args) {
        // 创建 random 实例
        Random random = new Random();

        // 1. 在 int 数据类型 内的随机数
        int x = random.nextInt();
        System.out.println(x);

        // 2. 设置获得的随机数的范围
        // 注意:是从 0 到 '你设置的边界'(可达到的最大数,不包括边界数)
        // 因为计算机总是从 0 开始计数
        int y = random.nextInt(10);
        System.out.println(y);

        // 3. 获取 5 ~ 15  之间的随机数
        // 最初的范围是 0 ~ 10 ， 都加上 5 之后
        // 范围变成 5 ~ 15
        int z = random.nextInt(10) + 5;
        System.out.println(z);

        // 4. 获取 1000 ~ 9999 之间的随机数
        int int_random_1 = 1000 + random.nextInt(10000 - 1000);
        System.out.println(int_random_1);

        // 5. 测试抽象出来的函数
        int int_ADT = random_range(1000,9999);
        System.out.println(int_ADT);
    }

    // 抽象为函数
    public static int random_range(int start, int finish){

        //Random random = new Random();
        //int int_random =  start + random.nextInt(finish + 1 - start);
        //return int_random;

        // 函数可以优化如下:
        return(
                new  Random().nextInt(finish + 1 - start) + start
                );
    }
    // 重载 random_range, 当之传入只有一个参数的时候,改为 从 0 开始，或者自定义开始
    public static int random_range( int finish){
        return(
                random_range(0, finish)
                );
    }
}

```

 

# Output

```
5
8
7072
6323
```

