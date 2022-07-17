## CSS学习记录

### background属性

> CSS背景图片的设置

https://blog.csdn.net/gf771115/article/details/79754431

这里一个很有用的地方就是图片与div区域的对齐方式（background-position: 50% 50%）

```css
div {
	background-position: 50% 50%;
}
```



**使用百分数定位时，其实是将背景图片的百分比指定的位置和元素的百分比位置对齐。**也就是说，百分数定位是改变了背景图和元素的对齐基点。不再像使用像素和关键词定位时，使用背景图和元素的左上角为对齐基点。

例如 background-position: 50% 50%; 就是将背景图片的 50%(center) 50%(center) 这个点，和div的 50%(center) 50%(center) 这个点对齐。如此做到居中的效果。

