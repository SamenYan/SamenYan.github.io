title: function add(a)(b)(c)有这样的写法吗？
date: 2016-07-23
tags:
    - js
---

#### 这个可以有。简单来说就是 add(a) 返回了一个函数，而将 b 作为参数去调用那个函数，又返回一个函数。

``` bash
function add(a) { 
    return function(b) { 
        return function(c) {
			return a+b+c;
    	}
    } 
} 
add(1)(2)(3); // 6
```
#### 同理,add(a)(b)的写法
	
``` bash
function add(a) { 
    return function(b) { 
        return a+b;
    } 
} 
add(1)(2); // 3 
```
#### 传统写法

``` bash   
function add(a,b) { 
    return a+b; 
} 
add(1,2); // 3
```