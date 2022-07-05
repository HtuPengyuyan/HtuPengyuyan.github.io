---
title: 初识XHR
date: 2022-07-05 13:13:58
tags:
---
## 使用FormDate
 #### 1. 通过 DOM 操作，获取到 form 表单元素
>  var form = document.querySelector('#form1')
    form.addEventListener('submit', function (e) {

 #### 2. 阻止表单的默认提交行为
> e.preventDefault()

#### 3. 创建 FormData，快速获取到 form 表单中的数据
> var fd = new FormData(form)
  var xhr = new XMLHttpRequest()
      xhr.open('POST', 'api')
      xhr.send(fd)
  xhr.onreadystatechange = function () {
        if (xhr.readyState === 4 && xhr.status === 200) {
          console.log(JSON.parse(xhr.responseText)) } }})

## 上传文件
```javascript
<!-- 1. 文件选择框 -->
  <input type="file" id="file1" />
  <!-- 2. 上传文件的按钮 -->
  <button id="btnUpload">上传文件</button>
  <br />
  <!-- 3. img 标签，来显示上传成功以后的图片 -->
  <img src="" alt="" id="img" width="800" />

  <script>
    // 1. 获取到文件上传按钮
    var btnUpload = document.querySelector('#btnUpload')
    // 2. 为按钮绑定单击事件处理函数
    btnUpload.addEventListener('click', function () {
      // 3. 获取到用户选择的文件列表
      var files = document.querySelector('#file1').files
      if (files.length <= 0) {
        return alert('请选择要上传的文件！')
      }
      var fd = new FormData()
      // 将用户选择的文件，添加到 FormData 中
      fd.append('avatar', files[0])

      var xhr = new XMLHttpRequest()
      xhr.open('POST', 'http://www.liulongbin.top:3006/api/upload/avatar')
      xhr.send(fd)

      xhr.onreadystatechange = function () {
        if (xhr.readyState === 4 && xhr.status === 200) {
          var data = JSON.parse(xhr.responseText)
          if (data.status === 200) {
            // 上传成功
            document.querySelector('#img').src = 'http://www.liulongbin.top:3006' + data.url
          } else {
            // 上传失败
            console.log('图片上传失败！' + data.message)
          }
        }
      }
    })
```
### 使用jQuery完成文件上传

```javascript
 $(function () {
      //（）[0]是将jQuery对象转化为dom对象
      //转换成dom对象才能进行访问files操作
      $('#btnUpload').on('click', function () {
        var files = $('#file1')[0].files
        if (files.length <= 0) {
          return alert('请选择文件后再上传！')
        }

        var fd = new FormData()
        fd.append('avatar', files[0])

        // 发起 jQuery 的 Ajax 请求，上传文件
        $.ajax({
            //上传文件用post请求
          method: 'POST',
          url: 'http://www.liulongbin.top:3006/api/upload/avatar',
          data: fd,
          //如果使用jQuery来上传文件的两个固定属性
          processData: false,
          contentType: false,
          success: function (res) {
            console.log(res)
          }
        })
      })
    })
```
### 初识axios并利用其发送请求
```javascript
   //发送get请求
   document.querySelector('#btn1').addEventListener('click', function () {
        var url = "http://www.liulongbin.top:3006/api/get"
        var paramsObj = { name: 'zs', age: 20 }
        axios.get(url, { parmams: paramsObj }).then(function (res) {
            console.log(res)
        })
    })
    //发送post请求
    document.querySelector('#btn2').addEventListener('click', function () {
        var url = "http://www.liulongbin.top:3006/api/post"
        var paramsObj = { address: '北京', location: '顺义区' }
        axios.post(url, { parmams: paramsObj }).then(function (res) {
            console.log(res)
        })
    })
    //直接利用axios发送请求
    document.querySelector('#btn3').addEventListener('click', function () {
        axios({
            method: 'GET',
            url: "http://www.liulongbin.top:3006/api/get",
            params: { name: 'zs', age: 20 }
        }).then(function (res) {
            console.log(res)
        })
    })
```


  
    
