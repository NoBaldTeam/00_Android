Markdown 学习
基本 Markdown 语法

1. 标题

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
2. 列表

 - 无序列表1
 - 无序列表2
 - 无序列表31. 有序列表12. 有序列表23. 有序列表3
3. 引用

 > 这个是引用
 > 是不是和电子邮件中的
 > 引用格式很像
4. 粗体与斜体

 **这个是粗体***这个是斜体*
5. 链接与图片

插入链接
inline style：
  [link text](http://example.com/ "optional title")
reference style：
 [link text][id]
 [id]: http://example.com/  "optional title here"
automatic link：
<http://example.com/> or <address@example.com>
插入图片
 ![](/path/to/img.jpg "optional title"){ImgCap}alt text{/ImgCap}
图片链接
 [![][jane-eyre-pic]][jane-eyre-douban]

 [jane-eyre-pic]: http://img3.douban.com/mpic/s1108264.jpg
 [jane-eyre-douban]: http://book.douban.com/subject/1141406/
6. 代码

用TAB键起始的段落，会被认为是代码块
      <php>
           echo “hello world";
      </php>
如果在一个行内需要引用代码，只要用反引号`引起来就好
 Use the `printf()` function.
7. 分割线

可以在一行中用三个以上的星号、减号、底线来建立一个分隔线
 ---
注：更详细的 Markdown 基本语法，请参考Markdown中文版语法说明
扩展 Markdown 语法（github扩展语法）

1. 删除线

 ~~Mistaken text.~~
2. 代码块与语法高亮

 ```ruby
 require 'redcarpet'
 markdown = Redcarpet.new("Hello World!")
 puts markdown.to_html
 ```
3. 表格

 | Tables        | Are           | Cool  |
 | ------------- |:-------------:| -----:|
 | col 3 is      | right-aligned | $1600 |
 | col 2 is      | centered      |   $12 |
 | zebra stripes | are neat      |    $1 |
4. 任务列表

 - [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> are supported
 - [x] list syntax is required (any unordered or ordered list supported)
 - [x] this is a complete item
 - [ ] this is an incomplete item
注1：更详细的 Markdown 扩展语法，请参考GFM（Github Flavored Markdown)
注2：GFM扩展语法并非所有的 Markdown 编辑器都支持。
其他高级用法

Cross-reference (named anchor) in markdown

 Take me to [pookie](#pookie)

 <a name="pookie"></a>
参考这里（http://stackoverflow.com/questions/5319754/cross-reference-named-anchor-in-markdown）
引用代码块中包含反引号

只需使用比代码块中反引号更多的连续反引号来实现
例如：引用 Markdown 代码区段：
 ```````
 print($abc, `abc`, ``ab``);

 ```````