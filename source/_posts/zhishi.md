---
layout: post
title: JS数组操作(数组增加、删除、翻转、转字符串、取索引、截取(切片)slice、剪接splice、数组合并)
date: 2017-11-17 14:02:19
tags: Javascript
toc: true
---
### POP 删除最后一项
```javascript
 var a = [1,2,3,4,5];
 a.pop(); //a：[1, 2, 3, 4]
 a.pop(); //a：[1, 2, 3]
 a.pop(); //a：[1, 2]
```
### shift 删除第一项
```javascript
 var a = [1,2,3,4,5]; 
 a.shift(); //a：[2,3,4,5]
 a.shift(); //a：[3, 4, 5]
```
<!-- more -->
### push 增加到最后
```javascript
 var a = [1,2,3,4,5]; 
 a.push(6); //[1, 2, 3, 4, 5, 6]
 aa.push('xx'); //[1, 2, 3, 4, 5, 6, "xx"] 返回长度7
 a.push('yy'); //[1, 2, 3, 4, 5, 6, "xx", "yy"] 返回长度8
```
### unshift增加到最前
```javascript
 var a = [1,2,3,4,5]; 
 a.unshift();//[1, 2, 3, 4, 5]
 a.unshift("cc");//["cc", 1, 2, 3, 4, 5] 返回长度6
 a.unshift("aaa");//["aaa", "cc", 1, 2, 3, 4, 5] 返回长度7
```
### reverse 数组翻转
```javascript
 var a = [1,2,3,4,5]; 
 a.reverse()//a：[5, 4, 3, 2, 1] 返回[5, 4, 3, 2, 1]
```
### join数组转成字符串
```javascript
 var a = [1,2,3,4,5]; 
 var b=a.join('||');//b:"1||2||3||4||5" a:[1,2,3,4,5] 
```
### indexOf数组元素索引
```javascript
 var a = ['a','b','c','d','e']; 
 a.indexOf('a');//0
 a.indexOf(a);//-1
 a.indexOf('f');//-1
 a.indexOf('e');//4
```
### slice截取(切片)数组 得到截取的数组
```javascript
 var a = ['a','b','c','d','e']; 
 a.slice(1,3);//["b", "c"] a:['a','b','c','d','e']
 a.slice(0,4);//["a", "b", "c", "d"]
 a.slice(3,4);//["d"]
```
### splice剪接数组 原数组变化 可以实现shift前删除，pop后删除,unshift前增加,同push后增加一样的效果,返回剪接的元素数组,原数组变化 ，索引从0开始
```javascript
 /*参数是2个*/
 //第一参数是索引（从0开始），第二是长度
 var a = ['a','b','c','d','e']; 
 a.splice(0,2);//["a", "b"] a:["c", "d", "e"]
 a.splice(0,2);//["c", "d"] a:["e"]
 var a = ['a','b','c','d','e']; 
 a.splice(0,1);//["a"] a:["b", "c", "d", "e"] 同shift前删除
 var a = ['a','b','c','d','e']
 a.splice(a.length-1,1)//["e"] a:["a", "b", "c", "d"] 同pop前删除
 /*参数大于2个*/
 //splice(start,deleteCount,val1,val2,...)：从start位置开始删除deleteCount项，并从该位置起插入val1,val2,... 
 var a = ['a','b','c','d','e']; 
 a.splice(3,1,10,21,238,99);//["d"] a:["a", "b", "c", 10, 21, 238, 99, "e"]
 var a = ['a','b','c','d','e']; 
 a.splice(a.length,100000000,88)//返回 [] 从最后元素后面的元素，截取长度任意个，肯定是空 a：["a", "b", "c", "d", "e", 88] 同push后增加
 var a = ['a','b','c','d','e']; 
 a.splice(a.length,0,88)//返回 [] 从最后元素后面的元素，截取长度任意个，肯定是空 a：["a", "b", "c", "d", "e", 88] 同push后增加
 var a = ['a','b','c','d','e'];
 a.splice(0,0,88,99)//返回 [] 从第一个元素，截取长度0个 肯定是空 a:[88, 99, "a", "b", "c", "d", "e"] 同unshift前增加
```
### concat数组合并
```javascript
 var a = ['a','b','c','d','e']; 
a.concat([88,99]);//["a", "b", "c", "d", "e", 88, 99] a:["a", "b", "c", "d", "e"]
var b= [9999,10000]
a.concat(b);// ["a", "b", "c", "d", "e", 9999, 10000] a:["a", "b", "c", "d", "e"]
```