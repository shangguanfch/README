# README
该文件用来测试和展示书写README的各种markdown语法。GitHub的markdown语法在标准的markdown语法基础上做了扩充，称之为`GitHub Flavored Markdown`。简称`GFM`。GFM在GitHub上有广泛应用，除了README文件外，issues和wiki均支持markdown语法。


* [横线](#横线)
* [标题](#标题)
* [文本](#文本)
	* [普通文本](#普通文本)
	* [单行文本](#单行文本)
	* [多行文本](#多行文本)
	* [文字高亮](#文字高亮)
	* [斜体 粗体 删除线](#斜体-粗体-删除线)
	* [换行](#换行)
* [图片](#图片)
* [链接](#链接)
	* [外部链接](#外部链接)
	* [本仓库链接](#本仓库链接)
	* [图片链接](#图片链接)
	* [锚点](#锚点)
* [列表](#列表)
	* [无序列表](#无序列表)
		* [使用无序列表](#使用无序列表)
		* [多级无序列表](#多级无序列表)
	* [有序列表](#有序列表)
		* [使用有序列表](#使用有序列表)
		* [有序列表自动排序](#有序列表自动排序)
		* [多级有序列表](#多级有序列表)
	* [复选框列表](#复选框列表)
* [表格](#表格)
	* [使用表格](#使用表格)
	* [对齐](#对齐)
	* [混合其他语法](#混合其他语法)
* [块引用](#块引用)
	* [常用于引用文本](#常用于引用文本)
	* [块引用有多级结构](#块引用有多级结构)
* [代码高亮](#代码高亮)
* [表情](#表情)
* [diff语法](#diff语法)
* [参考资料](#参考资料)

---


## 横线

`***`、`---`、`___`可以显示横线效果。3个或3个以上`*`、`-`、`_`的效果相同。

***
---
___

## 标题
语法：
```
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题  
```
效果：
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题  

## 文本
### 普通文本
这是一段普通的文本
### 单行文本
语法：在段落开头加入1个Tab或者4个空格。

    Hello,大家好，我是果冻虾仁。

### 多行文本
语法1：在连续几行的文本开头加入1个Tab或者4个空格。

    欢迎到访
    很高兴见到您
    祝您，早上好，中午好，下午好，晚安

语法2：使用一对各三个的反引号`` ` ``。
```
欢迎到访
很高兴见到您
祝您，早上好，中午好，下午好，晚安
```
语法2也可以实现代码高亮，见[代码高亮](#代码高亮)。
### 文字高亮
文字高亮功能能使行内部分文字高亮，使用一对反引号。语法：
```
`linux` `网络编程` `socket` `epoll`
```
效果：`linux` `网络编程` `socket` `epoll`

也适合做一篇文章的标签（tag）

### 斜体 粗体 删除线
语法|效果
|-|-
|`*斜体1*`|*斜体1*
|`_斜体2_`| _斜体2_
|`**粗体1**`|**粗体1**
|`__粗体2__`|__粗体2__
|`这是一个 ~~删除线~~`|这是一个 ~~删除线~~
|`***斜粗体1***`|***斜粗体1***
|`___斜粗体2___`|___斜粗体2___
|`***~~斜粗体删除线1~~***`|***~~斜粗体删除线1~~***
|`~~***斜粗体删除线2***~~`|~~***斜粗体删除线2***~~

    斜体、粗体、删除线可混合使用

### 换行
> 目前在GitHub中，英文空格和中文空格的效果不同，这会影响[换行](#换行)，以及[列表](#列表)。请尽量使用英文空格。

直接回车不能换行，（本括号后有1个回车）
可以在文本后面补两个空格，（本括号后有2个英文空格1个回车）  
这样下一行的文本就换行了。或者再加一个空行，（本括号后有2个回车）

也能实现换行效果，这实际上相当于另起新段落。

## 图片
格式：
```
![alt](URL title)
```
alt和title都可省略。alt和title对应HTML中的alt和title属性：
- alt表示图片显示失败时的替换文本
- title表示鼠标悬停在图片时的显示文本（注意title要有引号）

URL即图片的url地址。
- 使用网络图片地址。
- 使用本地仓库中的图片，直接使用**相对路径**就可以了。
- 使用其他github仓库中的图片，要注意格式：`仓库地址/raw/分支名/图片路径`，如：
  ```
  https://github.com/guodongxiaren/ImageCache/raw/master/Logo/foryou.gif
  ```

|#|语法|效果
|-|-|-
|1|`![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")`|![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")
|2|`![][foryou]`|![][foryou]

> 例2的写法使用了**URL标识符**的形式，[链接](#链接)一节有介绍。
在文末将`foryou`指向实际URL：
```
[foryou]: https://github.com/guodongxiaren/ImageCache/raw/master/Logo/foryou.gif
```

## 链接
### 外部链接
|#|语法|效果
|-|-|-
|1|`[我的博客](http://blog.csdn.net/guodongxiaren "悬停显示")`|[我的博客](http://blog.csdn.net/guodongxiaren "悬停显示")
|2|`[我的知乎][zhihu]`|[我的知乎][zhihu]

语法2由两部分组成：
- 第一部分使用两个中括号，[ ]里的标识符（本例中`zhihu`），姑且称之为**URL标识符**，可以是数字，字母等的组合。
- 第二部分将**URL标识符**指向实际URL。一般放在文末。
  ```
  [zhihu]:https://www.zhihu.com/people/jellywong "我的知乎，欢迎关注"
  ```
> **URL标识符**在`.md`文件渲染后不会显示。使用**URL标识符**能达到复用的目的，一般把**URL标识符**统一放在文末，这样看起来比较干净。
本文的**URL标识符**都放置于文末。

### 本仓库链接
|语法|效果
|-|-
|`[profile](./example/profile.md)`|[profile](/example/profile.md)
|`[profile](/example/profile.md)`|[profile](/example/profile.md)
|`[example](/example)`|[example](/example)
|`[example](example)`|[example](example)

### 图片链接
给图片加链接的本质是混合图片显示语法和普通的链接语法。普通的链接中[ ]内部是链接要显示的文本，而图片链接[ ]里面则是要显示的图片。  
直接混合两种语法当然可以，但是十分啰嗦，为此我们可以使用**URL标识符**的形式。

|#|语法|效果
|-|-|-
|1|`[![weibo-logo]](http://weibo.com/linpiaochen)`|[![weibo-logo]](http://weibo.com/linpiaochen)
|2|`[![](/images/zhihu.png "我的知乎，欢迎关注")][zhihu]`|[![](/images/zhihu.png "我的知乎，欢迎关注")][zhihu]
|3|`[![csdn-logo]][csdn]`|[![csdn-logo]][csdn]

- 因为图片本身和链接本身都支持**URL标识符**的形式，所以图片链接也可以很简洁（见例3）。
- 注意，此时鼠标悬停时显示的文字是图片的title，而非链接本身的title了。

### 锚点
每一个标题都是一个锚点，和HTML的锚点（`#`）类似，比如：

|语法|效果
|-|-
|`[回到顶部](#readme)`|[回到顶部](#readme)

不过要注意，标题中的英文字母都被转化为小写字母了。
> 以前GitHub对中文的支持不好，所以中文标题不能正确识别为锚点，但是现在已经没问题啦！

## 列表
> 目前在 GitHub 中，英文空格和中文空格的效果不同，这会影响[换行](#换行)，以及[列表](#列表)。请尽量使用英文空格。
### 无序列表
#### 使用无序列表
语法：`-`或`*`后空一格写字。
```
- 昵称：果冻虾仁
- 别名：隔壁老王
* 英文名：Jelly
```
效果：
- 昵称：果冻虾仁
- 别名：隔壁老王
- 英文名：Jelly

#### 多级无序列表
语法：在 `*` 或 `-` 钱加2、3或4个空格，或一个 Tab。
```
- 编程语言
  - 脚本语言
    - Python
      - OOP
```
```
- 编程语言
   - 脚本语言
      - Python
         - OOP
```
```
- 编程语言
    - 脚本语言
        - Python
            - OOP
```
效果：
- 编程语言
  - 脚本语言
    - Python
      - OOP

### 有序列表
#### 使用有序列表
语法：在数字后面加一个点，再加一个空格。
```
面向对象的三个基本特征：
1. 封装
2. 继承
3. 多态
```
效果：

面向对象的三个基本特征：
1. 封装
2. 继承
3. 多态

#### 有序列表自动排序
在第一行指定`1. `，而接下来的几行用`1. `就可以了，它会自动显示成2、3、4…。

面向对象的七大原则：
1. 开闭原则
1. 里氏转换原则
1. 依赖倒转原则
1. 接口隔离原则
1. 组合/聚合复用原则
1. “迪米特”法则
1. 单一职责原则

#### 多级有序列表
和无序列表一样，有序列表也有多级结构。语法：在`1. `前加3或4个空格。
```
1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
         1. 四级的有序列表显示效果，就不再变化了，依旧是英文字母
```
```
1. 这是一级的有序列表，数字1还是1
    1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
        1. 这是三级的有序列表，数字在显示的时候变成了英文字母
            1. 四级的有序列表显示效果，就不再变化了，依旧是英文字母
```
效果：
1. 这是一级的有序列表，数字1还是1
   1. 这是二级的有序列表，阿拉伯数字在显示的时候变成了罗马数字
      1. 这是三级的有序列表，数字在显示的时候变成了英文字母
         1. 四级的有序列表显示效果，就不再变化了，依旧是英文字母
### 复选框列表
语法：
```
- [x] 需求分析
- [x] 系统设计
* [x] 详细设计
* [ ] 编码
* [ ] 测试
- [ ] 交付
```
效果：
- [x] 需求分析
- [x] 系统设计
* [x] 详细设计
* [ ] 编码
* [ ] 测试
- [ ] 交付

可以使用这个功能来标注某个项目各项任务的完成情况。
> Tip: GitHub的**issue**中，可以实时点击复选框来勾选或解除勾选，而无需修改issue原文。

## 表格
### 使用表格
语法：
```
| 表头1  | 表头2|
| ---------- | -----------|
| 表格单元   | 表格单元   |
| 表格单元   | 表格单元   |
```
```
表头1  | 表头2|
----- ---- | --------|
表格单元  | 表格单元 |
表格单元  | 表格单元 |
```
```
表头1|表头2
-|-
表格单元|表格单元
表格单元|表格单元
```
效果：

表头1|表头2
-|-
表格单元|表格单元
表格单元|表格单元

### 对齐
表格可以指定对齐方式。语法：
```
| 左对齐        | 居中         | 右对齐    |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```

效果：

| 左对齐        | 居中         | 右对齐    |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |

### 混合其他语法
表格单元中的内容可以和大多数其他GFM语法配合使用，如：  
#### 使用普通文本的删除线，斜体等效果

|语法|效果
|-|-
| `~~Display the~~ help window.`| ~~Display the~~ help window.
| `_Closes_ a window`| _Closes_ a window 

#### 表格中嵌入图片（链接）
其实前面介绍图片显示、图片链接的时候，就是放在表格中显示的。

|语法| 图片
|-|-
`![baidu][baidu-logo]`| ![baidu][baidu-logo]

## 块引用
### 常用于引用文本
**文本摘自《深入理解计算机系统》 p. 27**
　  令人吃惊的是，在哪种字节顺序是合适的这个问题上，人们表现得非常情绪化。实际上术语“little endian”（小端）和“big endian”（大端）出自Jonathan Swift的《格利佛游记》一书，其中交战的两个派别无法就应该从哪一端打开一个半熟的鸡蛋达成一致。因此，争论沦为关于社会政治的争论。只要选择了一种规则并且始终如一的坚持，其实对于哪种字节排序的选择都是任意的。
> **“端”（endian）的起源**  
以下是Jonathan Swift在1726年关于大小端之争历史的描述：  
“……下面我要告诉你的是，Lilliput和Blefuscu这两大强国在过去36个月里一直在苦战。战争开始是由于以下的原因：我们大家都认为，吃鸡蛋前，原始的方法是打破鸡蛋较大的一端，可是当今的皇帝的祖父小时候吃鸡蛋，一次按古法打鸡蛋时碰巧将一个手指弄破了，因此他的父亲，当时的皇帝，就下了一道敕令，命令全体臣民吃鸡蛋时打破较小的一端，违令者重罚。”

### 块引用有多级结构
```
> 数据结构
>> 树
>>> 二叉树
>>>> 平衡二叉树
>>>>> 满二叉树
```
> 数据结构
>> 树
>>> 二叉树
>>>> 平衡二叉树
>>>>> 满二叉树

## 代码高亮
在三个反引号后面加上编程语言的名字（如：`bash`，`java`，`javascript`，`c`，`cpp`，`c++`），另起一行开始写代码，最后一行是三个反引号。
```bash
echo "hello GitHub" #bash
```
```java
public static void main(String[]args){} //java
```
```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```
```c
int main(int argc, char *argv[]) //c
```
```cpp
string &operator+(const string& A,const string& B) //cpp
```
```c++
string &operator+(const string& A,const string& B) //c++
```

## 表情
Github的Markdown语法支持添加emoji表情，输入不同的符号码（两个冒号包围的字符）可以显示出不同的表情。比如`:blush:`，显示为:blush:。

具体每一个表情的符号码，可以查询[EMOJI CHEAT SHEET](https://www.webpagefx.com/tools/emoji-cheat-sheet/)。因为这个网页每次都打开**奇慢**，所以整理到了本repo中，可以直接查看[emoji.md](/emoji.md)。

## diff语法
版本控制的系统中都少不了diff的功能，即展示一个文件内容的增加与删除。
GFM中可以显示的展示diff效果。使用绿色表示新增，红色表示删除。

其语法与代码高亮类似，只是在三个反引号后面写diff，
并且其内容中，以 `+ `开头表示新增，`- `开头表示删除。

效果：
```diff
+ 鸟宿池边树，僧敲月下门
- 鸟宿池边树，僧推月下门
```

## 参考资料
### [GitHub Help: Writing on GitHub](https://help.github.com/categories/writing-on-github/)
### [GitHub Guides: Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
### [Daring Fireball: Markdown Basics](https://daringfireball.net/projects/markdown/basics)


[csdn]:http://blog.csdn.net/guodongxiaren "我的博客"
[zhihu]:https://www.zhihu.com/people/jellywong "我的知乎，欢迎关注"
[weibo]:http://weibo.com/linpiaochen
[baidu-logo]:http://www.baidu.com/img/bdlogo.gif "百度logo"
[weibo-logo]:/images/weibo.png "点击图片进入我的微博"
[csdn-logo]:/images/csdn.png "我的CSDN博客"
[foryou]:https://github.com/guodongxiaren/ImageCache/raw/master/Logo/foryou.gif
