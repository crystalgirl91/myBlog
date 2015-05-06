#FileReader
使用FileReader对象,web应用程序可以异步的读取存储在用户计算机上的文件(或者原始数据缓冲)内容,
可以使用File对象或者Blob对象来指定所要处理的文件或数据.其中File对象可以是来自用户在一个<input>
元素上选择文件后返回的FileList对象,也可以来自拖放操作生成的 DataTransfer对象,
还可以是来自在一个HTMLCanvasElement上执行mozGetAsFile()方法后的返回结果.

##属性
* error DOMError	
	在读取文件时发生的错误. 只读.
* readyState 
	表明FileReader对象的当前状态. 值为State constants中的一个. 只读
* result 
	读取到的文件内容.这个属性只在读取操作完成之后才有效, 并且数据的格式取决于读取操作是由哪个方法发起的. 只读.

##方法
* abort()

中止该读取操作.在返回时,readyState属性的值为DONE.

* readAsArrayBuffer()

开始读取指定的Blob对象或File对象中的内容. 当读取操作完成时,readyState属性的值会成为DONE,
如果设置了onloadend事件处理程序,则调用之.同时,result属性中将包含一个ArrayBuffer对象以表示所读取文件的内容.

* readAsBinaryString()

开始读取指定的Blob对象或File对象中的内容. 当读取操作完成时,readyState属性的值会成为DONE,
如果设置了onloadend事件处理程序,则调用之.同时,result属性中将包含所读取文件的原始二进制数据.

* readAsDataURL()

开始读取指定的Blob对象或File对象中的内容. 当读取操作完成时,
readyState属性的值会成为DONE,如果设置了onloadend事件处理程序,
则调用之.同时,result属性中将包含一个data: URL格式的字符串以表示所读取文件的内容.

这个方法很有用,比如,可以实现图片的本地预览(在线演示):

	<input type="file"></input>
	<img src="">

	var result;
	var file = input.files[0];
	var reader = new FileReader;
	reader.onload = function(){
		result = this.result;
	};
	reader.readAsDataURL(file);
	document.querySelector("img").src = result;

* readAsText()

开始读取指定的Blob对象或File对象中的内容. 当读取操作完成时,readyState属性的值会成为DONE,如果设置了onloadend事件处理程序,则调用之.同时,result属性中将包含一个字符串以表示所读取的文件内容.


##事件处理程序
* onabort

当读取操作被终止时调用.

* onerror

当读取操作发生错误时调用.

* onload

当读取操作成功完成时调用.

* onloadend

当读取操作完成时调用,不管是成功还是失败.该处理程序在onload或者onerror之后调用.

* onloadstart

当读取操作将要开始之前调用.

* onprogress

在读取数据过程中周期性调用.