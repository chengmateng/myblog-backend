---
title: java IO classes and Objects
tags: java
categories: 计算机
abbrlink: 81c7
date: 2020-08-15 18:42:11
---

Objects in System class for interacting with a user:
System.out is a **PrintStream** object that outputs to the screen.

System.in is an **InputStream** object that reads from the keyboard.

**readLine** is defined on BufferedReader Objects
 ### How do we construct a BufferedReader? With an InputStreamReader.==(Compose into entire lines of text)==
 ### How do we construct an InputStreamReader? With an InputStream.==(Compose into characters)==
 ### How do we construct an InputStream? System.in is one.==(Reads raw data)==

Figure this out via online Java libraries API-java.io

Example1:
```js
import java.io.*;
class SimpleIO {
	public static void main(String[] args) throws Exception{
    	BufferedReader kybd = new BufferedReader(new InputStreamReader(System.in));
        System.out.println(kybd.readLine());
    }
}

```

Example2:
```js
import java.util.Scanner;
public class Main{
	public static void main(Strign[] args){
    	Scanner scanner = new Scanner(System.in);//创建 scanner 对象
        System.out.println("Input your name: ");//打印提示
        String name = scanner.nextLine();//读取一行输入并获取字符串
        int age = scanner.nextInt();// 读取一行输入并获取整数
        System.out.println("Hi, %s, you are %d\n", name, age);
    }
}
```
