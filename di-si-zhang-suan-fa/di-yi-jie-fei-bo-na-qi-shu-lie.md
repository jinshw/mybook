# 第一节 斐波那契数列

* ## 题目描述

一只青蛙一次可以跳上1级台阶，也可以跳上2级。求该青蛙跳上一个n级的台阶总共有多少种跳法

**第一种方法**

```js
function  cal(n){
    if(n<=0){
        return -1;
    }
    if(n==1||n==2){
        return n;
    }else{
        return cal(n-1)+cal(n-2);
    }
}
```

**第二种方法**

```js
function JumpFloor(n){
if(n<0){
    return 0
}
var fibArry = [0,1,2]
if(n<3){
  return fibArry[n]
}
var nReturn;
var fibFirst=1,fibTow=2;
for (var i = 3; i <= n; i++)             
  {
      nReturn =fibFirst + fibTow;                 
      fibFirst=fibTow ;
      fibTow = nReturn;
  }            
  return nReturn;
}
```

---

* ## 题目描述

  一只青蛙一次可以跳上1级台阶，也可以跳上2级……它也可以跳上n级。求该青蛙跳上一个n级的台阶总共有多少种跳法。

假设f\(n\)是n个台阶跳的次数。

**解析：**

1. f\(1\) = 1

2. f\(2\) 会有两个跳得方式，一次1阶或者2阶，这回归到了问题f\(1\),f\(2\) = f\(2-1\) + f\(2-2\)

3. f\(3\) 会有三种跳得方式，1阶、2阶、3阶，那么就是第一次跳出1阶后面剩下：f\(3-1\);第一次跳出2阶，剩下f\(3-2\)；第一次3阶，那么剩下f\(3-3\).因此结论是  
   f\(3\) = f\(3-1\)+f\(3-2\)+f\(3-3\)

4. f\(n\)时，会有n中跳的方式，1阶、2阶...n阶，得出结论：

f\(n\) = f\(n-1\)+f\(n-2\)+...+f\(n-\(n-1\)\) + f\(n-n\) =&gt; f\(0\) + f\(1\) + f\(2\) + f\(3\) + ... + f\(n-1\) == f\(n\) = 2\*f\(n-1\)

所以，可以得出结论

![](https://segmentfault.com/img/bVp56n)

java实现

```java
public class Solution {
    public int JumpFloorII(int target) {
        if(target==0){
            return 0;

        }
        if(target==1){
            return 1;
        }
        return 2*JumpFloorII(target-1);
    }
}
```

javascript实现

```js
function JumpFloorII(n){
    if(n==0)
        return 0;
    if(n==1)
        return 1;
    return 2*JumpFloorII(n-1);
}
```

---

* ## 题目描述

我们可以用2\*1的小矩形横着或者竖着去覆盖更大的矩形。请问用n个2\*1的小矩形无重叠地覆盖一个2\*n的大矩形，总共有多少种方法？

**解析：斐波那契数列**

1. f（1）=1
2. f（2）=2
3. f\(n\)=f\(n-1\)+f\(n-2\)

**java实现**

```java
public class Solution {
    public int RectCover(int target) {
        if(target==0){
            return 0;
        }
        if (target == 1) {
            return 1;
        }
        if (target == 2) {
            return 2;
        }
        return RectCover(target - 1) + RectCover(target - 2);

    }
}
```

**javascript实现**

第一种方式：递归

```js
function RectCover(n){
    if(n==0){
        return 0;
    }
    if(n==1){
        return 1;
    }
    if(n==2){
        return 2;
    }

    return RectCover(n-1)+RectCover(n-2);

}
```

第二种方式：循环

```js
function rectCover(n)
{
    if(n==0||n==1||n==2){
        return n;
    }

    var nReturn;
    var one = 1,two = 2;
    for(var i=3;i<=n;i++){
        nReturn = one + two;
        one = two;
        two = nReturn;
    }
    return nReturn;
}
```

> **关联知识：源码、补码、反码**
>
> * 计算机中的符号数有三种表示方法，即**原码、反码和补码**。三种表示方法均有符号位和数值位两部分，符号位都是用0表示“正”，用1表示“负”，而数值位，三种表示方法各不相同
>
> * **特征：**
>
> 1、一个负整数（或原码）与其补数（或补码）相加，和为模。
>
> 2、对一个整数的补码再求补码，等于该整数自身。  
> 3、补码的正零与负零表示方法相同。
>
> * **求补码：\(a\) 正数的补码与源码相同 . （b） 负整数的补码**，将其对应正数二进制表示所有位取反（包括符号位，0变1，1变0）后加1
> * *



