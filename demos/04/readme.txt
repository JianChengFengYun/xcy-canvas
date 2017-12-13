【SVG】
	在HTML5出现之前就有；
	SVG：矢量图；
	SVG的扩展名：“.svg”;
	SVG使用的是XML语法；
概念：
	SVG是一种使用XML技术描述二维图形的语言；
特点：
	SVG绘制的图形可以被搜索引擎抓取；
	图片质量不下降的情况下无线放大；不失帧；

SVG VS Canvas
	Canvas绘制的是一张图片；
	多用SVG -- 减少外部链接
       * SVG
         * 不依赖分辨率
	 * 支持事件绑定
	 * 大型渲染区域的程序(例如百度地图)
	 * 不能用来实现网页游戏
       * Canvas
         * 依赖分辨率
	 * 不支持事件绑定
	 * 最合适网页游戏
	 * 保存为".jpg"格式的图片
	如图 
用途：
	网页中的小图标；
	网页中的动态效果；

1.svg元素种类
	使用svg，先写<svg></svg>标签;
	利用svg绘制图形，必须定义在svg标签内；
	利用svg绘制的图形，与HTML页面有关；可以用dom获取元素，可以加事件；
	***svg提供的属性cx,cy....只读，不能操作；
	- 预定义元素；
		-- 矩形：<rect />
		   属性：
		      x,y,width,height,fill,stroke,stroke-width;
		   ** width,height 必须使用属性方式，不能使用style样式；
		      style="fill:blue;stroke:white;stroke-width:5;" 
		      svg绘制元素，用style，使用的不是css属性，而是svg自己的属性；

		-- 圆形：<circle />
		   属性：
			cx,cy 圆心；
			r，fill,stroke,stroke-width;

		-- 椭圆：<ellipse />
		   属性：
			cx,cy 圆心；
			rx,ry 半径
			fill,stroke,stroke-width;
		
		-- 直线：<line />
		   属性：
			x1,y1 起点；
			x2,y2 终点
			stroke,stroke-width;

		-- 折线：<polyline />
		   属性：
		        points:多个坐标点，空格隔开；x,y用“,”隔开；
				points="x1,y1 x2,y2 x3,y3"
			fill,stroke,stroke-width;
		   特点：
		        默认折线区域(起点到终点)是黑色；fill="white";
		
		-- 多边形：<polygon />
		   属性：
		        points:多个坐标点，空格隔开；x,y用“,”隔开；
				points="x1,y1 x2,y2 x3,y3"
			fill,stroke,stroke-width;

	- 特效元素
		-- 渐变 
		   渐变元素要定义在<defs></defs>标签内；
		   --- 线性渐变 <linearGradient></linearGradient>
		       属性：
			    x1,y1,x2,y2: 值是百分比；
		       使用<stop />设置渐变位置，颜色和透明度；
		       属性：
			    offset： 值是百分比；0可以不是；
			    stop-color:
			    stop-opacity:

			   <defs>
				<linearGradient id="orange">
					<stop />
				</linearGradient>
			   </defs>
			   <rect fill="url(#orange)" />
		  --- 径向渐变 <radialGradient></radialGradient>		
		  
		-- 滤镜 高斯模糊 
		   <filter></filter>
		   元素要定义在<defs></defs>标签内；
		   滤镜定义在元素<feGaussianBlur />
		       属性：
		       in="SourceGraphic";固定写法；
		       stdDeviation="5"   模糊程度；
			   <defs>
				<filter id="orange">
					<feGaussianBlur in="SourceGraphic" stdDeviation="5" />
				</filter>
			   </defs>
			   <rect filter="url(#orange)" />
2.使用js库
	Three.js	绘制三维图形
	Two.js		绘制二维图形 http://jonobr1.github.io/two.js/
	Two.js支持的格式
		- svg	默认；
		- canvas
		- WebGL
	如何使用Two.js；
		在HTML页面中引入two.js文件
		在HTML页面中定义容器(<div>)
		在javascript代码中
		获取HTML页面中的容器
		创建Two对象,将该对象添加到容器中
		new Two(params).appendTo(Element);
		使用two.js提供的API方法进行绘制
		利用two.js提供的方法,设置图形
		利用update()方法进行绘制
	创建Two对象
		构造器 - new Two(params)
		params参数 - 设置当前对象的信息
			type - 设置当前使用的格式(Two.Types.svg)
			svg - 默认值
			canvas
			webgl
			width和height - 设置宽度和高度
			fullscreen - 设置是否全屏
			Boolean值,true表示全屏
	图形方法
		makeLine() - 绘制线条
		makeRectangle() - 绘制矩形
		makeCircle() - 绘制圆形
		makeEllipse() - 绘制椭圆
	动画方法
		update() - 更新动画
		play() - 添加动画(循环)
		pause() - 删除动画
	设置绘制图形的样式
		调用Two对象的绘制方法绘制图形时,返回该图形对象
		通过该图形对象,设置相关属性值
	分组操作
		Two.Group
	动画效果
		bind(event,callback)方法 - 事件绑定
			event - 绑定事件名称
			update - 对应update()方法的作用
	所有的DOM事件都可以绑定
	callback - 事件处理函数

