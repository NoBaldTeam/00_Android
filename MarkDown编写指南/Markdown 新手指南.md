为知笔记 Markdown 新手指南

2015-11-23 产品与服务
Markdown 是什么

Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。它允许人们「使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档 」—— 维基百科

如果你看不懂以上维基百科对 Markdown 的定义，就当这段掐了没播。约翰·格鲁伯自己对Markdown的描述的重点也在于 「easy-to-read，easy-to-write」。

那么到底 easy 在哪里呢？

虽然称作 「标记语言」，但简单理解 Markdown 就是在文本前增加符号来表示文本格式。你不需要关心标题多大号，列表缩进多少，是否对齐，只要使用了同一种符号标记，Markdown 已经帮你做好了排版。

无图无真相：

![](http://pbdkyxc0r.bkt.clouddn.com/f74c65a27f205226e6f2808af6568029.png)

Markdown 的好处

编辑，不用操心排版你只需要把注意力放在内容上。笔者在用 Markdown 之前，打开word 先想想，标题用啥字体呢，几号字呢？不知不觉我的意志力就被消耗了。实际上所谓排版，不就是作者的思路以及内容的层级和结构么，在学会使用 Markdown 之后，几个简单的符号就把这些事儿搞定，样式还特别工整精美。
修改，不用担心排版想想那些你在同事之间改来改去的 word 文档吧，如果哪位童鞋从外部粘贴了一段带格式的文字，那么你再次打开文档时会发现整个人都不好了：格式被改的乱七八糟，还要重新调整。如果用 Markdown 群组笔记 ，想改哪里改哪里，根本不用担心格式，改完评论里直接 @TA，多轻松！
一句话来说，Markdown 是用最简单的方式，零排版成本，写出布局工整、阅读舒适的笔记。减少干扰，降低成本，提高效率，不管在什么设备上，看起来都是一个工整的样子。不仅自己阅读爽，分享给朋友也有面儿不是~

那些牛人都在用

阳志平在 2012 年就发博客推崇了一下 Markdown，但那篇文章虽解读深刻，但也略显极客，把Markdown 不仅能排版，能做流程图，还支持数学公式的特性介绍了一遍，连科技论文都要选择 Markdown 都涉猎到了。有兴趣阅读的童鞋可点击这里查看。

很多在线博客和内容社区都提供 Markdown 编辑器，不仅在阅读上带来了舒适、统一、美好的体验，每一个参与写作的人，也能够毫不费力地写出排版整齐的文章来。

如何在为知笔记上创建 Markdown 笔记

为知笔记所有客户端都支持 Markdown ，有两种方法可以创建 Markdown 笔记

第一种：在笔记标题后面加 .md ，编辑并保存后，即可看到渲染后的效果
第二种：在移动端直接创建 Markdown 笔记
编辑完成后，点击 「保存」 按钮，即可看到格式精美的笔记啦！

来个小技巧

不管我再怎么说 Markdown 的语法记忆负担小、简单，在最初你都会有点儿晕。在这里给大家分享个小技巧：

最初只需要记住 # 标题一、## 标题二、1. 第一点、* 这一点，用这几个写写日志、需求文档、小文章，排版上足够了；
逐渐的你发现有些文字需要重点指出，那么还可以使用 **加粗**、*斜体* 来对文字做重点说明；
如果你是名程序员，那么可以用 ``` 把代码块包起来，渲染后可以关键字高亮，用 > 可以做引用 ；
学生的话，就去了解一下 LaTex 吧，为知笔记 Markdown 支持 Mathjax 公式渲染哦~
Markdown 格式标记符号说明

1. 标题

在行首插入 1 到 6个#，分别表示标题 1 到标题 6


# 这是标题1
## 这是标题1
###### 这是标题6
点击保存后的效果：

标题1

标题2

标题6

2. 有序列表

在行首增加 1.、2.、3.，即数字和英文句点, 不要求数字一定要连续，可以都是1.


1. 有序列表
1. 有序列表
4. 有序列表
点击保存后的效果：

有序列表
有序列表
有序列表
3. 无序列表

在行首增加 * 或 -


* 无序列表
* 无序列表
点击保存后的效果：

无序列表
无序列表
4. 插入图片

可直接粘贴图片，或将图片文件拖动到光标处。

也可以使用标准的Markdown语法，如：
 ![](http://cdn.wiz.cn/wp-content/uploads/2015/06/wiz_logo.png)

5. 插入链接

[描述](链接地址) ，例如：[为知笔记](http://www.wiz.cn)，注意要使用英文符号
点击保存后的效果：
为知笔记

6. 粗体、斜体、删除线

粗体：在文字前后添加 ** (注意符号与文字间不要有空格）
斜体：在文字前后添加 *
删除线：在文字前后添加 ~~

**粗体**
*斜体*
~~删除线~~
保存后的效果：

粗体
斜体
删除线

7. 引用

在文字前 添加 >

点击保存后的效果：

如果你无法简洁的表达你的想法，那只说明你还不够了解它。 -- 阿尔伯特·爱因斯坦

8. 表格

| 为知笔记|更新 | 版本 |
|------------|-----------|--------|
| WizNote | Markdown| Latest |
点击保存后的效果：

为知笔记	更新	版本
WizNote	Markdown	Latest
9. 代码

在代码前后增加 三个反单引号：```


```
int i = 0; i = 1; 
for (int i = 0; i < 100; i++)
{
      printf("hello markdown!\n");
}
```
保存后的效果：

![](http://pbdkyxc0r.bkt.clouddn.com/24ffa42aad4a399a2d3d5675de0e8ea9.png)

10. 目录

在任何你想要展示Markdown 笔记目录的地方，添加 [TOC] ， 在阅读模式下，标题1~6样式的内容会被提取出来作为目录，相当于大纲功能。

例如：

[TOC]

###Markdown 是什么

####Markdown 的好处

点击保存后的效果：

![](http://pbdkyxc0r.bkt.clouddn.com/QQ20151123-2.png)

11. Mathjax 公式

可以创建行内公式，例如：$\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$
或者块级公式，
$$ x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$
点击保存后的效果：

![](http://pbdkyxc0r.bkt.clouddn.com/c3dd8cb47ba6fa86cdeb005f10c324d6.png)

12. 流程图

```flow
st=>start: Start
e=>end: End
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes or No?
io=>inputoutput: catch something...
st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
```

保存后效果：

![](http://pbdkyxc0r.bkt.clouddn.com/QQ20151123-0.png)

注意：
1) 关键词（start、end、operation、subroutine、condition和inputoutput）后的冒号后要紧跟一个空格。
2) 使用->来连接两个元素，对于condition类型，有yes和no两个分支，如示例中的cond(yes)和cond(no)。

更多关于流程图的语法说明：http://adrai.github.io/flowchart.js/

13. 时序图

```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```
保存后效果：

![](http://pbdkyxc0r.bkt.clouddn.com/QQ20151123-1.png)

更多关于时序图的语法说明：http://bramp.github.io/js-sequence-diagrams/
