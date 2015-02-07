<!DOCTYPE html>
<html>
<title></title>
#transform 2D
###transform语法：transform:[translate() || rotate() || scale() || skew() || martrix()]
释：transform的变形方式可叠加作用
	#object {
	    transform-origin: 0 0;
	    transform: rotate(15deg)  translateX(230px)  scale(1.5, 2.6)  skew(220deg, -150deg)
	}
<span id="transtate">
##translate()位移函数
</span>
###translate参数语法：translate(tx,ty) || translate(tx) || translateX(tx) || translateY(ty)
* tx是一个代表X轴（横坐标）移动的向量长度，当其值为正值时，元素向X轴右方向移动，反之其值为负值时，元素向X轴左方向移动。
* ty是一个代表Y轴（纵向标）移动的向量长度，当其值为正值时，元素向Y轴下方向移动，反之其值为负值时，元素向Y轴上方向移动。如果ty没有显式设置时，相当于ty=0。

<span id="rotate">
##rotate()旋转函数
</span>
###rotate参数语法：rotate(a)
* a：代表的是一个旋转的角度值。其取值可以是正的，也可以是负的。如果取值为正值时，元素默认之下相对元素中心点顺时针旋转；如果取值为负值时，元素默认之下相对元素中心点逆时针旋转。

<span id="scale">
##scale()缩放函数
</span>
###scale参数语法：scale(sx) || scale(sx,sy) || scaleX(sx) || scaleY(sy)
* sx：用来指定横向坐标（X轴）方向的缩放向量，如果值为0.01~0.99之间，会让对象在X轴方向缩小，如果值大于或等于1.01，对象在X轴方向放大。
* sy：用来指定纵向坐标（Y轴）方向的缩放量，如果值为0.01~0.99之间，会让对象在Y轴方向缩小，如果值大于或等于1.01，对象在Y轴方向放大。如果未显式的设置这个值，默认与第一个值相等。
* 参数取负值时，会先让元素进行翻转，然后在进行缩放。

<span id="skew">
##skew()变形函数
</span>
###参数语法：skew(ax,ay) || skew(ax)
* ax：用来指定元素水平方向（X轴方向）倾斜的角度。
* ay：用来指定元素垂直方向（Y轴方向）倾斜的角度。如果未显式的设置这个值，其默认为０。

##matrix()矩阵函数
##兼容性
CSS3的2D变形到目前为止在主流浏览器中得到较好的支持.但在实际使用的时候需要添加浏览器各自的私有属性：
* IE9中使用2D变形时，需要添加-ms-私有属性，在IE10+版本开始支持标准版本。
* Firefox3.5至Firefox15.0版本需要添加-moz-的私有属性，在Firefox16+版本开始支持标准版本。
* Chrome4.0+开始支持2D变形，在实际使用的时候需要添加-webkit-私有属性。
* Safari3.1+开始支持2D变形，在实际使用的时候需要添加-webkit-私有属性。
* Opera10.5+开始支持2D变形，在实际使用的时候需要添加-o-私有属性，但在Opera12.1版本不需要添加私有属性，不过在Opera15.0+版本需要添加私有属性-webkit-私有属性。
* 移动设备iOS Safari3.2+、Android Browser2.1+、Blackberry Browser7.0+、Opera Mobile14.0+、Chrome for Android25.0+需要添加私有属性-webkit-，而Opera Mobile11.0至Opera Mobile12.1和Firefox for Android19.0+不需要使用浏览器私有属性。
</html>
