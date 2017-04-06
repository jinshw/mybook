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

**解析：**

1. f（1）=1
2. f（2）=2
3. f\(n\)=f\(n-1\)+f\(n-2\)

java实现

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





