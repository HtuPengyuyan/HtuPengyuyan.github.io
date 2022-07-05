---
title: “关于markdown”
date: 2022-06-30 16:52:45
tags:
---
我展示的是一级标题(使用=和-)
===============
我展示的是二级标题
----------
使用#号标记
# 一级标题
## 二级标题
### 三级标题
#### 四级标题

# 关于Markdown段落
第一次使用Markdown   

首次使用Markdown


# 关于Markdown的几种字体
*斜体文字*
**粗体文字**
***粗斜体文字***

# 分隔线
***
---
# 脚注
创建脚注格式类似这样[^RUNOOB]。
[^RUNOOB]: 菜鸟教程 -- 学的不仅是技术，更是梦想！！！

# Markdown列表
## 无序列表
* 第一项
* 第二项
* 星号后面记者加空格
## 有序列表
1. 第一项
2. 第二项
3. 使用数字并加上.表示
## 列表的嵌套
1. 第一项
    * 第一项的第一个元素
    * 秩序在子列表选项前加四个空格
2. 第二项
    * 第二项的嵌套元素
# Markdown区块
> 区块引用
> 使用区块
### 区块可以嵌套
>最外层
>>第一层嵌套
>>> 第二层嵌套

# Markdown代码
`if()`如果段落上的一个函数或片段用反引号把他包裹起来
#### 用```包裹一段代码，可以指定一种语言
```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

# Markdown 链接
这是我的github链接[HtuPengyuyan](https://github.com/HtuPengyuyan)
或者可以直接使用链接地址
> <https://github.com/HtuPengyuyan>

### 高级链接

通过变量设置一个链接,变量赋值在文档末尾进行：
这个链接用1作为网址变量[HtuPengyuyan]([1])
[1]:https://github.com/HtuPengyuyan

<!-- <img src='img' width='200px'> -->

![](/img/logo.png)

# Markdown表格
| 表头 | 表头 |
| --- | ---|
|单元格|单元格|
|单元格|单元格|
