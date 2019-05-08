---
title: HTML知识点总结
date: 2019-04-23 21:48:16
tags:
  - web
comments: true
categories: web
---

HTML，超文本标记语言（英语：HyperText Markup Language的简称），是一种用于制作网页的标准标记语言。
网站开发经常会使用到HTML的各种标签，下面是对常用的一些知识点的总结。

思维导图：

![HTML](/images/html/HTML.png)

## 块级元素（block）

- div 块容器
- h1,h2,h3,h4,h5,h6 内容的标题
- p 段落
- form 表单
- ul 无序列表
- ol 有序列表
- li 列表项目
- table 表格
- canvas 画布
- video 视频

## 行内元素（inline）

- a 超链接
- span 文本
- img 图片
- br 换行
- input 输入元素
- label 表单标签
- select 下拉列表
- textarea 文本区域
- button 按钮

## inline-block元素

- iframe 内联框架


## form表单

- input 输入元素

| type | 说明 |
|--------|--------|
|   text     |    文本输入框     |
|   password     |    密码输入框     |
|   radio     |    单选框     |
|   checkbox     |    复选框     |
|   submit     |    提交按钮     |
|   button     |    按钮     |
|   file     |    文件上传对象     |
|   hidden     |    隐藏输入域     |
|   image     |    image图片元素     |
|   reset     |    重置按钮     |

- select 下拉列表

```html
<select>
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="opel">Opel</option>
  <option value="audi">Audi</option>
</select>
```

- textarea 文本区域
- button 按钮
- hidden 隐藏域

## table表格
- thead 表头
- tbody 表格主题
- tfoot 表格页脚（部分浏览器支持）
- tr 表格中的一行
- th 表头单元格
- td 标准单元

示例：
```html
<table>
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Footer content 1</td>
      <td>Footer content 2</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>
</table>
```

## HTML文本格式化
- 粗体`<b>`,加重语气`<strong>`
- 斜体`<i>`,着重文字`<em>`
- 大号字体`<big>`,小号字体`<small>`
- 下标`<sub>`,上标`<sup>`
- 预格式文本`<pre>`
- 改变文字方向`<bdo dir="rtl>`
- 长块引用`<blockquote>`,短块引用`<q>`
- 删除文本`<del>`,插入文本`<ins>`

