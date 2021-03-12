[TOC]

# 1. 链表

## 1.1. 链表是什么?

- 链表是由多个元素组成的列表
- 元素存储不连续,用`next`指针连在一起

看下面的图示:

<img src="https://tva1.sinaimg.cn/large/007S8ZIlgy1giyousgotzj30b001ymwz.jpg"/>

可以看到每个链表中的元素都有一个`next`指针指向了下一个元素

## 1.2. 数组 VS 链表

> 既然链表也是多个元素组成的列表,和数组差不多为啥还要有链表呢?其实它们差异大着呢,下面我们简单分析一下:

- **数组**:增删非首尾元素时往往需要移动元素(例如在中间添加一个元素,后面所有的元素都要往后移动一位,在中间删除一个元素则后面的所有元素都要往前移动一位,比较消耗性能!)
- **链表**:增删非首尾元素,不需要移动元素,只需要更新`next`的指向即可,非常的方便!

## 1.3. JS 中的链表

> 注意:在 JS 中没有链表这种数据结构,但是我们可以使用`Object`来模拟链表!

### 1.3.1. 使用 JS 来实现一个链表

```javascript
// 初始化4个元素,并链起来.如此就形成一个链表
const a = { val: "a" };
const b = { val: "b" };
const c = { val: "c" };
const d = { val: "d" };
a.next = b;
b.next = c;
c.next = d;

// 遍历链表 p 是一个指针
let p = a;
while (p) {
  console.log(p.val);
  p = p.next;
}

// 在上面的链表中插入一项 e,很简单.只需要把 c 的 next 指针指向 e,然后把 e 的 next 指针指向 d.这样就在链表中间插入了一个新的元素
const e = { val: "e" };
c.next = e;
e.next = d;

// 删除
c.next = d;
```

使用`js`来实现的链表,如下图所示,可以发现是一个深层嵌套的对象:
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gjv0mia5llj307305ja9y.jpg)

## 1.4. Leetcode 上有关链表的题

[237:删除链表中的节点](https://leetcode-cn.com/problems/delete-node-in-a-linked-list/)
[206:反转链表](https://leetcode-cn.com/problems/reverse-linked-list/)
[2:两数相加](https://leetcode-cn.com/problems/add-two-numbers/)
[83.删除排序链表中的重复元素](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/)
[141.环形链表](https://leetcode-cn.com/problems/linked-list-cycle/)

> TIPS:这些入门经典题的讲解暂时不用听也来得及,先把基本概念搞清楚,然后回过头来继续刷题!

## 1.5. 前端与链表

> 前端与链表的结合点:`原型链`!

### 1.5.1. 原型链

> 原型链的简介:

- 原型链的本质是链表
- 原型链上的节点是各种原型对象,比如:`Function.prototype`,`Object.prototype`...
- 原型链通过 `__proto__` 属性链接各种原型对象

### 1.5.2. 原型链长啥样?

> 如下代码所示:

```javascript
// 对象
obj -> Object.prototype -> null

// 函数
func -> Function.prototype -> Object.prototype -> null

// 数组
arr= -> Array.prototype -> Object.prototype -> null
```

## 1.6. 使用链表指针获取 JSON 的节点值

> 废话不多说,我们直接看代码:

```javascript
const json = {
  a: { b: { c: 1 } },
  d: { e: 2 },
};

const path = ["a", "b", "c"];

let p = json;
path.forEach((k) => {
  p = p[k];
});
```

## 1.7. 链表总结

- 链表中的元素不是连续的,他们之间通过`next`指针进行链接!这是链表和数组最大的区别之处
- 在 `js` 中没有链表这个原生数据结构,但是我们可以用 `Object` 来模拟链表
- 链表的常用操作:`修改 next`,遍历链表

# 2. leetcode 链表板块

> 屁话不多说,就是一个字:刷!

[leetcode linked-list module](https://leetcode-cn.com/tag/linked-list/)
