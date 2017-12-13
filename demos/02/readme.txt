
画布Canvas：HTML5提供的新元素；
	Canvas在HTML页面中提供画布的功能；
	在画布中绘制各种图形：
	Canvas绘制的图形与html页面无关，无法通过DOM获取绘制的图形，无法为绘制的图形绑定DOM事件；只能使用Canvas提供的API；********
	Canvas用途：
		在HTML中绘制图表（如柱状图，饼状图）
		网页游戏--
	Canvas 默认300px*150px；

	如何使用：
	1.在页面定义Canvas元素；
		Canvas元素：使用行内样式定义Canvas元素的宽高，会对绘制出的图形的尺寸有影响，
			    建议使用属性width="500"，或css文件；*************
	2.在js中：
		  获取Canvas元素；
		  创建画布对象；
			getContext("2d")方法；返回画布对象；
					参数-表示创建的2d效果还是3d效果；
					参数类型是string类型；-->"2d" "3d"
			通过该对象使用Canvas提供的API方法；
		  绘制图形；
	绘制图形：
	1.绘制矩形：
		- fillRect(x,y,width,height)	实心矩形 默认颜色是黑色；
			x,y:矩形左上角坐标值；
		- strokeRect(x,y,width,height)	空心矩形	默认边框宽度为1px；
		- clearRect(x,y,width,height)	清除指定区域的矩形
		设置颜色：
		- fillStyle	设置填充颜色
		- strokeStyle	描边颜色
		- globalAlpha	透明度（0-1）
		颜色渐变：
		- 线型渐变	createLinearGradient(x1,y1,x2,y2)
			具有基准线；起点(x1,y1)和终点(x2,y2)；
			**返回渐变对象；通过这个对象设置渐变颜色；
			addColorStop(position,color);
				position:渐变的位置；0-1之间；
				color:颜色；

		- 射线渐变	createRadialGradient(x1,y1,r1,x2,y2,r2)
			具有柱形（锥形）-两个圆的面积
			x1,y1：第一个圆的圆心坐标；
			r1：第一个圆的半径
			x2,y2：第二个圆的圆心坐标；
			r2：第二个圆的半径
			**返回渐变对象；