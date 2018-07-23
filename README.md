<h2>vue筛选器组件</h2>

```
<filteredBox :tagArr="tagArr" @deleteTag="deleteTagFilter"></filteredBox>
```

<div>父组件需要提供类似上述props给filterBox。deleteTag是为了实现删除功能父组件提供的方式。</div>
<h4>筛选框效果：</h4>

![image](https://github.com/wangc1993/filteredBox/blob/master/filteredBox.png)
