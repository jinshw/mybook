* ## 题目描述

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有的奇数位于数组的前半部分，所有的偶数位于位于数组的后半部分，并保证奇数和奇数，偶数和偶数之间的相对位置不变。

**解析：**

> **输入：**
>
> 每个输入文件包含一组测试案例。  
> 对于每个测试案例，第一行输入一个n，代表该数组中数字的个数。  
> 接下来的一行输入n个整数。代表数组中的n个数。
>
> **输出：**
>
> 对应每个测试案例，  
> 输入一行n个数字，代表调整后的数组。注意，数字和数字之间用一个空格隔开，最后一个数字后面没有空格。
>
> **样例输入：**
>
> ```
> 5
> 1 2 3 4 5
> ```
>
> **样例输出：**
>
> ```
> 1 3 5 2 4
> ```
>
> 对于普通的交换顺序，只要设两个指针分别从头跟尾扫描，当分别遇到不符合条件的位置时停止，然后交换位置，这样只要时间O\(n\)，空间O\(1\)，但是这样做会改变原来的顺序，要保持原来的位置，可以借用一个队列，先将一类数放到正确的位置上，再将队列里的数放到剩下的位置。时间仍为O\(n\)，但是要用额外空间，大小取决于输入。最坏情况下空间为O\(n\)。

**第一种方法（复杂）**

```js
function reOrderArray(array)
{

    if(array == null){
        return []
    }
    var len = array.length;
    var temp=0;
    var _index = 0;
    for(var i=0;i<len;i++){
        _index = i;
        if(array[i]%2>0){
            _index = i;
            continue;
        }else{//偶数

            for(var j=i+1;j<len;j++){
                if(array[j]%2>0){
                    temp = array[_index]
                    array[_index] = array[j]
                    array[j] = temp

                }else{
                    _index = j;
                    continue;
                }
            }

        }    
    }
}
```

**第二种方法：**

```js
function reOrderArray(a){
    var arryA = []
    var arryB = []

    for(var i=0;i<a.length;i++){
        if(a[i]%2>0){
            arryA.push(a[i])
        }else{
            arryB.push(a[i])
        }
    }
    a.splice(0,a.length)
    for(var k=0;k<arryA.length;k++){
        a.push(arryA[k])
    }
    for(var k=0;k<arryB.length;k++){
        a.push(arryB[k])
    }

return a

}
```



