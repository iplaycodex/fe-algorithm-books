[TOC]

# 1. 集合

集合是一种`无序且唯一`的数据结构,划重点:**无序且唯一!**

`ES6` 中有`集合`,名为`Set`,是 ES6 新增的一种数据结构!

集合的常用操作:去重,判断某个元素是否在集合中,求交集

...

## 1.1. 集合常用操作

**1.去重**

```javascript
// 去重
let arr = [1, 1, 2, 2, 3];
let newArr = [...new Set(arr)];
```

可以看到使用`Set`来去重是非常的简单且方便的!

**2.判断元素是否在这个集合中**

```javascript
let set = new Set([1, 2, 3]);
console.log(set.has(1)); //set 集合中是否包含1,输出 true
```

**3.求交集**

```javascript
// 求交集
let set = new Set([1, 2, 3]);
const set2 = new Set([2, 3]);
const set3 = new Set([...set].filter((item) => set2.has(item)));
```

> 更多有关 ES6 集合的知识请查阅阮一峰老师的博客:
> [es6 set 数据结构](https://es6.ruanyifeng.com/#docs/set-map)

## 1.2. Leetcode 真题

[349.取两个数组的交集](https://leetcode-cn.com/problems/intersection-of-two-arrays/)

```javascript
// 取两个数组的交集这个算法题很简答,看下面的代码:
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var intersection = function (nums1, nums2) {
  // 利用 Set 数据结构来去重,实现求交集的一个算法
  let set1 = new Set(nums1);
  let set2 = new Set(nums2.filter((item) => set1.has(item)));
  return [...set2];
};
```

## 1.3. 前端与集合(学习一下 Set 的一些 API)

> 学习一下 Set 数据结构的一些常用 API

废话不多说,直接看代码:

```javascript
// 新建一个空的 set
let mySet = new Set();

// 给 set 中添加元素
mySet.add(1);
mySet.add(5);
mySet.add(5);
mySet.add("some text");
let o = { a: 1, b: 2 };
mySet.add(o);
mySet.add({ a: 1, b: 2 }); //对象因为引用不同所以可以重复添加

// 判断集合中是否有某个元素
const has = mySet.has(o); //输出:true

// 集合中删除某个元素
mySet.delete(5);

// 遍历集合
for (let [key, value] of mySet.entries()) {
  console.log(key, value);
}

// 集合转换为数组
const myArr = Array.from(mySet);

// 数组转换为集合
const mySet2 = new Set([1, 2, 3, 4]);

// 去交集
const intersection = new Set([...mySet].filter((x) => mySet2.has(x)));

// 求差集
const difference = new Set([...mySet].filter((x) => !mySet2.has(x)));
```

## 1.4. 参考资料

[ES6 中新增数据结构:Set](https://www.runoob.com/w3cnote/es6-map-set.html)

# 2. 集合重点:无序且唯一!!!
