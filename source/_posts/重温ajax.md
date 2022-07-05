---
title: 重温ajax
date: 2022-07-02 10:42:56
tags:
---
### 关于聊天机器人发起请求获取聊天消息
```javascript
function getMsg(text){
    $.ajax({
        method:'get',
        url:'',
        data:{
            spoken:text
        },
        success:function(res){
            if(res.message==='success'){
                var msg=res.data.info.text  # 调取成功后的内容存放在res.data.info.text里
                $('$talk_list').append('<li class="left_word"><img src="img/person01.png">'/><span>'+msg+'</span><li>')
                resetui(); # 输完内容后滚动条在最下面
            }
        }
    })
}
```