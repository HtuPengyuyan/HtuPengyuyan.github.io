---
title: 重温xhr
date: 2022-07-02 11:25:26
tags:
---
### 关于xhr的get和post请求
##### 1.创建xhr对象
> var xhr =new XMLHttpRequest()
##### 2.调用open函数 #用来指定请求方式和url地址
> xhr.open('get','http://www.HtuPengyuyan.github')
##### post请求多一步Content-Types属性（固定写法）
> xhr.setRequestHeader('Content-Type','application/zx-www-form-urlenooded')
##### 3.调用send函数，发起Ajax请求
> xhr.send()
##### 4.监听onreadystatechange事件
> xhr.onreadystatechange=function(){
    //监听xhr对象的请求状态 readyState ； 与服务器相应的状态 status
> if( xhr.readyState === 4 && xhr.status===200){
    //代表获取数据成功
    console.log(xhr.responseText);
}    
}