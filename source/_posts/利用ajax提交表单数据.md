---
title: 利用ajax提交表单数据
date: 2022-07-05 01:48:40
tags:
---
### 创建表单
```javascript
  <form action="/login" id="f1">
    <input type="text" name="user_name" />
    <input type="password" name="password" />
    <button type="submit">提交</button>
  </form>
```
### 监听表单元素拿到表单的值
##### 1.其中e.preventDefault()为阻止表单默认提交行为
##### 2.$('#f1').serialize()获取表单元素
##### 3.使用serialize()函数时必须给表单加name的值，否则无法提取表单元素
```javascript
    $('#f1').on('submit', function (e) {
        e.preventDefault()
        var data = $('#f1').serialize()
      $.post("接口",data,function(){
        if(res.status!==201){}
      })
      })
```
