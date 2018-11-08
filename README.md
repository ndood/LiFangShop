# LiFangShop
## 项目描述
	> 本项目为H5混合开发App商城项目,同时适配手机端Android系统和ios系统
## 主要模块
	> 卖家管理系统：管理商品、订单、类目、商品规格属性、用户管理以及内容发布等功能
	> 买家系统：用户可以在系统中进行浏览商品、首页、下单、支付等操作
	> 配送系统：配送员可根据商圈进行筛查订单，接单并且进行配送任务，以及代收等操作
	> 登录系统: 为多个系统之间提供用户登录凭证以及查询登录用户的信息
	> 订单系统: 提供下单、查询订单、修改订单状态、定时处理订单
	> 购物车系统: 集中管理订单
	> 搜索系统：提供商品的搜索功能
## 应用技术
	> 前端：采用mui框架进行开发，通过cordova来调用原生app功能以及配合打包app。
## 遇到问题（）
	> 长按闪退问题
		情景还原：商品列表页，长按列表页的列表项时(触摸到文字)，在低版本手机中会出现闪退的情况
		解决：
			```
			js:e.preventDefault();
			css:-webkit-touch-callout: none; //解决闪退
				//禁止复制
				-moz-user-select: none;
				-khtml-user-select: none;
				user-select: none;
			```
	> 移动端1px问题
		解决：使用css解决1px的问题，并且给需要设置成1px的dom元素直接写上：border-width:1px;
	> click事件在ios中有问题
		问题描述：click事件在ios点击触发时，会选中事件委托的父级元素模块【即：由于事件冒泡，并且父级有默认样式】
					并且有一个透明层
		解决：添加e.stopPropagation(); //阻止冒泡
				如果还是无法解决问题，可以修改成touch事件
	> 原生js的事件监听和jquery的事件绑定在ios中失效
		问题描述：使用事件监听或事件绑定时，由于父元素选择body或document元素，导致在ios中事件触发无效
		解决：不使用body和document元素作为父级元素
	> ios中日期显示为NaN
		问题描述：Date的日期格式，在ios中有兼容性问题，ios的日期会显示成：NaN
		解决：在ios中支持"2017/12/26 19:36:00"，而不支持"2017-12-26 19:36:00"格式，后面一种格式，在ios中显示Nan （Android中都可以显示正常）
	


