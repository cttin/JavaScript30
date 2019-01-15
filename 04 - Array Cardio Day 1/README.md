# 03 数组方法1
## 简介
这部分主要是熟悉数组的几个方法，包括：filter、map、sort、reduce。
## 知识点
* filter
语法：
`arr.filter(callback(element[, index[, array]])[, thisArg])`。
详情参考[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* map
语法：
```
arr.map(function callback(currentValue[, index[, array]]) {
    // Return element for new_array
}[, thisArg])
```
详情参考[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
和filter类似，filter也接收一个函数，返回一个数组，不同的是filter()把传入的函数依次作用于每个元素，然后根据返回值是true还是false决定保留还是丢弃该元素。
map()方法将调用的数组的每个元素传递给指定的函数，并返回一个数组。如果是稀疏数组，返回的也是相同方式的稀疏数组：它具有相同的长度，相同的缺失元素。
* sort
语法：
`arr.sort([compareFunction])`。
接收一个函数作为参数,函数的参数分别为第一个和第二个元素。方法用于对数组的元素进行排序,并返回数组。默认排序顺序是根据字符串Unicode码点。要实现这一点，首先应把数组的元素都转换成字符串（如有必要），以便进行比较。
V8 引擎 sort 函数只给出了两种排序 InsertionSort 和 QuickSort，数量小于10的数组使用 InsertionSort，比10大的数组则使用 QuickSort。
[V8引擎Array源码](https://github.com/v8/v8/blob/ad82a40509c5b5b4680d4299c8f08d6c6d31af3c/src/js/array.js) （710行开始）
* console.table
* 把nodeList转化为数组
可以使用解构赋值和Array.from等方式，这里推荐Array.from，相对来说较为语义化。
