# 03 CSS变量
## 简介
CSS变量可以利用JS来实时更新，意味着当你更新CSS变量时，和它相关的变量都会自动更新。如果你使用SAS，你需要在编译阶段定义它，编译之后你不能改变它。
## 实现思路如下：
* 在CSS中全局（:root）声明三个变量，一个是用input标签控制的内边距spacing，一个是用input标签控制的背景颜色base，还有一个同样是input控制的滤镜效果。
* 把这三个变量分别应用于img标签和JS字体中。
* 获取页面上所有的input标签，分别绑定change和mousemove事件，事件处理函数的逻辑是根据自定义属性来获取改变值的单位。获取根元素html，给其赋值标签上name所含的属性，值为`this.value`。
* 鼠标改变value值得时候将会触发页面更新。
## 解决难点
* 自定义属性data-sizing设置为padding和滤镜的单位，通过`this.dataset`获取`sizing`属性。
* 如何改变CSS变量的值。通过`document.documentElement`设置根元素的style属性值（html标签渲染后的效果为`style="--blur:6px; --spacing:155px;"`），这样CSS变量有改动的时候，页面会立即更新。
## 知识点
* NodeList 和 Array
可以在proto查看其方法，Array所具有的方法比NodeList多。如果使用NodeList已经具有的方法，不建议把NodeList转化为数组。
* 自定义属性
标签中自定义属性`data-`及HTML5中自定义数据属性dataset。
* CSS变量
声明方式（--变量名）及使用语法（var(--变量)）。这是css3新特性，目前IE和Edge不支持。
* 伪类
:root伪类
* CSS滤镜filter
CSS 的滤镜提供了一些图形特效，比如高斯模糊、锐化、变色等。它带有一些预设的函数，在使用时加上参数调用这些函数即可。
## 拓展
假设直接给元素`<span>JS</span>`的父元素h2设置属性`style="--base: #BADA55"`，JS字体的颜色是不会随着--base改变而改变的。因为h2标签距离`JS`更近，它的优先级更高，所以JS字体的颜色就是`#BADA55`。而图片的内边距颜色还是随着鼠标改变`--base`的值而变化，因为img标签的祖先元素是html。

