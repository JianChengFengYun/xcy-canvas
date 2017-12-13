Canvas 绘制图形
1.绘制文字
	方法:
	fillText(text,x,y) - 实心文字
		text - 绘制的文字内容
		x和y - 绘制的坐标值
	strokeText(text,x,y) - 空心文字
	属性:
	font - 类似于CSS中的font属性
	textAlign - 设置文字的水平方向对齐
		left - 左对齐
		center - 水平居中
		right - 右对齐
	textBaseline - 设置文字的垂直方向对齐
		top - 顶部对齐
		middle - (垂直)居中对齐
		bottom - 底部对齐
		hanging - 悬挂基线
		alphabetic - 字母基线
	注意:
	无论是水平方向还是垂直方向对齐,基准线对齐,并不是文字对齐
	无论是水平方向还是垂直方向对齐,并不是必要的属性(不使用也是可以的)
2.阴影效果
	shadowColor - 设置阴影颜色
	shadowOffsetX - 设置水平方向阴影
	shadowOffsetY - 设置垂直方向阴影
	shadowBlur - 设置阴影的模糊程度
3.创建路径
	(标识)方法
	beginPath() - 表示开始创建路径
	closePath() - 表示结束创建路径
4.设置方法
	rect(x,y,width,height) - 设置矩形形状
		x和y - 设置矩形的左上角坐标值
		width和height - 设置矩形的宽度和高度
	arc(x,y,radius,startAngle,endAngle,direction) - 设置圆形形状
		x和y - 设置圆形的圆心坐标值
		radius - 设置圆形的半径
		startAngle和endAngle - 设置圆形的起始位置
		direction - 按照顺时针或逆时针绘制
5.绘制方法
	stroke() - 绘制轮廓
	fill() - 绘制填充
6.绘制线条(直线和折线、多边形) - 创建路径
	moveTo(x,y) - 设置这条线的起点坐标值
	lineTo(x,y) - 设置这条线的终点(折点)坐标值
	stroke()

7.设置线条
	lineWidth - 设置线条的宽度
		默认值为1(px)
	lineCap - 设置线条端点的形状
		butt - 默认值,平直
		round - 圆角
		square - 正方向
	lineJoin - 设置两条线焦点的形状
		miter - 默认值,尖角
		round - 圆角
		bevel - 斜角
	miterLimit - 配合lineJoin使用
	lineJoin设置为miter,该属性值设置尖角的延伸范围

8.Canvas处理图片
	- 绘制图片
	drawImage(img,x,y) - 按照图片原大小加载
		img - 当前加载(绘制)的图片
		x和y - 绘制图片的坐标值(左上角)
	drawImage(img,x,y,width,height) - 按照指定大小加载图片
		img - 当前加载(绘制)的图片
		x和y - 绘制图片的坐标值(左上角)
		width和height - 设置绘制图片显示的宽度和高度
	注意
	必须保证图片加载完毕(onload事件)后,再绘制图片

	- 平铺图片
	createPattern(img,type)
		img - 平铺的图片
		type - 平铺的方式
			repeat - 平铺
			no-repeat - 不平铺
			repeat-x - 水平方向平铺
			repeat-y - 垂直方向平铺
	注意
	必须保证图片加载完毕(onload事件)后,再绘制图片
	- 切割图片
	clip() - 切割(按照创建路径使用)
9.画布方法
	scale(x,y) - 缩放(缩小或放大)
		x - 表示水平方向的缩放
		y - 表示垂直方向的缩放
		参数的取值
		如果为1的话,表示不缩放(原大小)
		如果小于1的话,表示缩小
		如果大于1的话,表示放大
	translate(x,y) - 重新定位(x,y)
		x和y - 新的坐标值
		注意 - x和y是相对于上次定位坐标值
	rotate(旋转角度) - 旋转画布
		公式为 degrees  Math.PI / 180;

【Chart.js - Canvas的JS库】
作用 - 提供各种图表
如何使用
	在HTML页面中引入Chart.js文件
	在HTML页面中定义<canvas>元素
	在javascript代码中
	获取<canvas>元素
	创建画布对象
	var context = canvas.getContext("2d");
	通过画布对象,创建Chart对象
	var chart = new Chart(context);
	利用Chart对象调用API方法
	var data = [];
	chart.Pie(data);
提供6种图表
柱状图 - Bar(data,options)
饼状图 - Pie(data,options)
曲线图 - Line(data,options)
环形图 - Doughnut(data,options)
雷达图 - Radar(data,options)
极地区域图 - PolarArea(data,options)
