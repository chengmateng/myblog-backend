---
title: Sieve of Eratosthenes Agorithm
tags: java
categories: 计算机
abbrlink: e509
date: 2020-09-21 18:42:11
---

埃拉托斯特尼筛法是一种用来找出一定范围内素数的方法。
例如，如果要输出2到100内所有质数。
具体算法是先把2到100全部放入一个数组内，并标记为true。
然后divisor从2开始增加，
对于每一个divisor，例如divisor=2，则，4（2×divisor），6，8，10，。。。到n，全都标记为false，
然后在divisor++, divisor=3, 则，6（2×divisor），9，12，。。。，到n，全都标记为false，等等等等，直到divisor×divisor＜n。

``` javascript
import java.util.Scanner;
public class SieveOfEratosthenes {
    public static void main(String[] args){
        Scanner scanner= new Scanner(System.in);
        System.out.println("请输入一个数： ");
        int n=scanner.nextInt();

        boolean[] prime = new boolean[n+1];
        int i;
        for(i=2;i<=n;i++){
            prime[i]=true;
        }

        for(int divisor =2; divisor*divisor<=n;divisor++) {
            if (prime[divisor]) {
                for (i = 2 * divisor; i <= n; i = i + divisor) {
                    prime[i] = false;


                }
            }

        }
        for(i=2;i<=n;i++){
            if(prime[i]){
                System.out.println(" "+i);
            }
        }
   }
}
```

