[TOC]

# 1. 字典

## 1.1. 字典的概念

字典是什么?`字典`与集合类似,字典也是易总存储唯一值得数据结构,但是它是以`键值对`的形式来存储的

令人欣喜的是在`ES6`中添加了字典,就是`Map`!!!真是喜大普奔啊!

字典的常用操作:键值对的增删改查

## 1.2. Map 的操作

```javascript
// 新建一个 map
const m = new Map();

// 增
m.set("a", "aa");
m.set("b", "bb");

// 删
m.delete("b");
// m.clear();

// 改
m.set("a", "aaa");

// 差
m.get("a");
```

## 1.3. Leetcode 字典真题

[349.两个数组的交集](https://leetcode-cn.com/problems/intersection-of-two-arrays/)
[20.有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)
[3.无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)
[76.最小覆盖串](https://leetcode-cn.com/problemset/all/?search=76)

## 1.4. 相关资料

[ES6 中新增的数据结构:Map](https://www.runoob.com/w3cnote/es6-map-set.html)
