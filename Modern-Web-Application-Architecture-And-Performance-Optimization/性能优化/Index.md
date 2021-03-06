[![返回目录](https://parg.co/US3)](https://parg.co/UGZ) 
 

# Web 应用性能优化
Web 应用优化

我们首先需要了解

总的优化策略会从[资源请求与缓存、关键渲染路径、图片优化、脚本解析与执行、页面布局与渲染策略、交互与动画、移动端优化、PWA]()等几个角度进行考虑。



广义的性能优化



# 性能调优始于设计
在前端项目中，我们常常与产品经理以及UI设计讨论如何在美感与性能之间达到平衡，我们坚信更快地内容呈现是好的用户体验的不可分割的一部分。在我们自己的网站中，我们是以性能优于美感。好的内容、布局、图片与交互都是构成你网站吸引力的不可或缺的部分，不过这些复杂的元素的使用往往也意味着页面加载速度的增加。设计的核心即在于决定我们网站需要呈现哪些内容，往往这里的内容会指图片、字体这样的偏静态的部分，我们首先也从对于静态内容的优化开始。

## Static Site Generator
为了演示与测试方便，我们基于NodeJS搭建了一个混合使用MarkDown与JSON作为配置的静态网站生成器，其中一个简单的博客类型的网站的配置信息如下:
```
{
  "keywords": ["performance", "critical rendering path", "static site", "..."],
  "publishDate": "2016-08-12",
  "authors": ["Declan"]
}
```
而其内容为:
```
# A case study on boosting front-end performance
At [De Voorhoede](https://www.voorhoede.nl/en/) we try to boost front-end performance...
## Design for performance
In our projects we have daily discussions...
```
下面，我们就这个静态网站，进行一些讨论。