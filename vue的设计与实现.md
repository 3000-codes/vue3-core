# vue的设计与实现

## 第一章 框架设计概览

### 1.1 命令式

```js
// 在app中创建一个div，内容为hello world
const app=document.getElementById('app')
const box=document.createElement('div')
box.innerHTML='hello world'
app.appendChild(box)
```

### 1.2 声明式

```js
// 在app中创建一个div，内容为hello world
const app=document.getElementById('app')
const box={
    tag:'div',
    children:'hello world'
}
app.appendChild(box)
```

### 1.3 虚拟DOM
  
```vue
<template>
    <div>
        <div :class="'className'" v-if="show" @click="handler">{{msg}}</div>
    </div>
</template>
```
```js
// 转换为 类似于下面的对象
const box={
    tag:'div',
    children:[{
        tag:'div',
        attrs:{
            class:'className'
        },
        if:show,
        on:{
            click:handler
        },
        children:msg
    }]
}
```

### 1.4 运行时(runtime)





