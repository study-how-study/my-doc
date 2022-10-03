**行内元素有哪些、块级元素有哪些、空元素有哪些**
- 行内元素: span img input
- 块级元素：div footer header section p h1...h6、...
- 空元素：br、hr
- 块级元素独占一行

```
  display:inline;
  display:inline-block;
  display:block;
```
**页面导入样式时，使用link和@import的区别**
- 现有link后有@import (link兼容ie浏览器)
- 先加载link后加载@import

**title和h1的区别**
- title是网站标题，h1是网站内容
- title告诉搜索引擎网站的内容主题是什么，h1告诉搜索引擎内容最主要是什么
- title更重要
- 一般网站的logo使用h1包裹
  
**b和strong的区别**
- b只有加粗，strong有强调语气
- strong在盲人网页阅读时语气加重
- b尽量少用

**i和em的区别** 
- i只有文字倾斜，strong有强调语气
- i用在字体图标，em用在术语(医药、生物)
  
**img标签属性title和alt的区别** 
- title是鼠标移入时显示、alt为图标报错时显示
- alt用于seo搜索，用于描述图片，方便蜘蛛抓取

**图片格式png jpg gif webp区别** 
- png为无损压缩，体积比jpg大，适合做小图标
- 采用压缩算法，有一点失真，体积小
- gif做动图、很少用
- webp同时支持有损和无损压缩，体积更小，兼容性不好


