# 第一节 斐波那契数列

* 题目描述

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



