#### 绝对定位元素的垂直居中实现
1.需要知道具体宽高，然后利用margin调节

```
.container {
			position: absolute;
			left: 50%;
			top: 50%;
			margin-top: -100px;
			margin-left: -200px;
			width: 400px;
			height: 200px;
		}
```

2.使用trasnsform: trasnslate(-50%, -50%);

```
.container {
			position: absolute;
			left: 50%;
			top: 50%;
			trasnsform: trasnslate(-50%, -50%);
			width: 400px;
			height: 200px;
		}
```

3.使用margin: auto;

```
.container {
			position: absolute;
			left: 0;
			top: 0;
			right: 0;
			bottom: 0;
			margin: auto;
			width: 400px;
			height: 200px;
		}
```

这其实是和水平居中margin : 0 auto;原理是一致的，只是`left: 0;top: 0;right: 0;bottom: 0;`会让人感到比较疑惑。先单独对上下即`top: 0;bottom: 0;`来说：

```
‘top’ + ‘margin-top’ + ‘border-top-width’ + ‘padding-top’ + ‘height’ + ‘padding-bottom’ + ‘border-bottom-width’ + ‘margin-bottom’ + ‘bottom’ = height of containing block
```

因为`margin: auto;`所以上下的margin就把剩下的高度平分，从而达到了垂直居中的目的。对于水平居中也是一样的原理。

详情可以参考张鑫旭的[小tip: margin:auto实现绝对定位元素的水平垂直居中](http://www.zhangxinxu.com/wordpress/2013/11/margin-auto-absolute-%E7%BB%9D%E5%AF%B9%E5%AE%9A%E4%BD%8D-%E6%B0%B4%E5%B9%B3%E5%9E%82%E7%9B%B4%E5%B1%85%E4%B8%AD/comment-page-1/#comment-351461)和在该博文下的30、31楼评论，评论里有[W3C](http://www.w3.org/TR/CSS2/visudet.html#abs-non-replaced-height)关于这方面标准的链接。要加强对标准规范的熟悉和理解了~