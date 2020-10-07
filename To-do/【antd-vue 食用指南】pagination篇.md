---
title: 【antd-vue 食用指南】 pagination 篇
date: 2020-09-20 12:12:04
tags: 
  - 组件使用
categories: 
  - antd-vue 食用指南

---

> 在平常工作生活中，经常就会遇到一些要修改 antd 组件内部封装好的显示需求，比如分页组件就会遇到只显示5页的需求，修改下拉框显示的需求。但去网上找，有的很难找到，有的只告诉你一声是什么 API 而没有实现，所以本文面向 **伸手党** ，会告诉你一些 antd 官网没有说清楚的配置方法，并给出实例。

## 组件介绍

一个满配的 pagination 组件大概长下面这样 →

![pagination 组件](https://photoeditor.oss-cn-chengdu.aliyuncs.com/%E5%9B%BE%E7%89%871.png)

众所周知，pagination 有两种使用方法，一种是直接写 `<a-pagination/>` 另外一种是挂载到 table 上 `:pagination="pagination"` ，本文也会从这两种方式来介绍配置方法，请放心食用。

## 官网文档能解决的需求

### 国际化相关

- 下拉框显示**条/页**
- Go to 变为 **跳至□页**

[指路文档](https://www.antdv.com/components/locale-provider-cn/)

### API 基础配置相关

- [基本 API](https://www.antdv.com/components/pagination-cn/#API)
- [表格配置](https://www.antdv.com/components/table-cn/#pagination)

## 如何自定义下拉选项

### 插槽

[文档指路](https://www.antdv.com/components/pagination-cn/#%E8%87%AA%E5%AE%9A%E4%B9%89%E4%B8%8B%E6%8B%89%E9%80%89%E9%A1%B9)

### pagination 配置

模板:

```html
<template>
  <a-table :columns="columns" :data-source="data" :pagination="pagination""/>
</template>
```

配置：

```javascript
pagination: {
    pageSize: 10,
    showSizeChanger: true,
    buildOptionText: props => <strong>{props.value} items/page</strong>
}
```

在配置项里配置下拉选项通过 **buildOptionText**  (props) => vNode 接口，就可以在里面用 jsx 语法书写要返回的 虚拟DOM，下拉选项就可以随意配置了。

实例：

https://codesandbox.io/s/eloquent-feather-qms9p?file=/src/components/table.vue

## 如何自定义页码

### 常见需求1——只显示5个页码的分页组件



