# 添加文章置顶

请在 `path-to-your-blog/node_modules/hexo-generator-index/lib/generator.js` 的合适位置添加如下代码：

```js
posts.data = posts.data.sort(function(a, b) {
      if(a.top && b.top) {
          if(a.top == b.top) return b.date - a.date;
          else return b.top - a.top;
      }
      else if(a.top && !b.top) {
          return -1;
      }
      else if(!a.top && b.top) {
          return 1;
      }
      else return b.date - a.date;
  });
```

如代码所示，“置顶” 功能只是实现了按照文章 top 值排序的功能。