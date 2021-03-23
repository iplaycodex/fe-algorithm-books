# 每日一题

> 今天的题目是一道跟数组有关的算法题,也是笔者面试中遇到的一个题目.算是 easy 难度的吧.在这里写一下:

# 题目

找出两个数组中相同的元素,eg:

```javascript
// 找出下面2个数组中的相同元素,例本测试用例,则输出:[3,6,7],写一个算法实现这个功能
let a = [1, 3, 5, 6, 7];
let b = [2, 3, 6, 7, 8];
```

# 算法题解如下所示

```javascript
function findDiffElement(arr1, arr2) {
    // 合并两个数组
    let midArr = [...arr1, ...arr2];
    // 遍历合并后的数组,利用数组的 includes api 去查找被遍历的元素是否已经存在在临时数组中,如果不存在则 push 至 tempArr,
    // 存在的话则说明它就是重复的元素,则将其push至 resultArr 中
    let tempArr = [];
    let resultArr = [];
    midArr.forEach((item) => {
        if (!tempArr.includes(item)) {
            tempArr.push(item);
        } else {
            resultArr.push(item);
        }
    });
    return resultArr;
}
```
