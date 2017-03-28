#### 基本实现思路是

```
<div class="team-name"></div>

<div class="content">
	<div class="team-members"></div>
	<div class="team-intro"></div>
</div>	
```

1.先让.team-name左浮动（或者使用绝对定位)，然后给.content其设置一个合适的margin-left.

2.然后在.content里面，让.team-members右浮动（不能使用绝对定位），.team-intro保持在normal-flow内，给其设置合适的margin-right。

原因是：任务要求“改变中间一栏的内容长度，以确保在中间一栏较高和右边一栏较高时，父元素的高度始终为子元素中最高的高度。” 于是，这时候就只能让.team-members浮动了，因为可以通过清除浮动来“恢复高度”，而绝对定位是完全脱离normal-flow的。而且.team-intro也不要使用浮动，因为当其所在容器宽度不够的时候，它会“跑下来”，而我们要的是他们的顶部保持对齐。