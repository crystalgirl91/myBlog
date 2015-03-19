#apply and call

在JS中每个函数对象都有内置方法apply和call。
##apply语法:Function.apply(Objthis,ArrParam);

* Function:函数对象
* Objthis:对象，Function对象的this将会指向这个新对象Objthis，而不再指向调用这个Function的对象。
* Arrparam:数组，Function的参数集合。也可以传入argumets对象。可以为空。

看例子：

    var obj1 = {name:"obj1",func:function(){console.log(111,this.name)}}
    var obj2 = {name:"obj2",func:function(){console.log(222,this.name)}}
    obj2.func()                               //输出结果：222,"obj2"
    obj2.func.apply(obj1)                     //输出结果：222,"obj1"
    
    
    

从上面可以看出，声明了obj1,obj2两个对象，两个对象都有name属性和fuc方法，执行obj2的func方法时调用内置apply方法，这使得函数func的this指向了obj1,而不再是调用该方法（func）的对象obj2.

  * 函数的this默认始终指向调用该函数的对象，但是通过apply可以改变this的指向。

##call语法：Function.apply(Objthis,parames);
  call方法与apply方法大同小异，主要的区别是两个函数接受参数的方式不一样，apply方法接受数组作为参数，而call则接受多个以逗号分隔的参数。
  
  例如：
  
    var arr = [1,2,3,4,5];
    Math.max(1,2,3,4,5)               //返回5
    Math.max(arr)                     //返回NaN
    Math.max.call(null,1,2,3,4,5)     //返回5
    Math.max.apply(null,arr)          //返回5
    
  上例中Math.max方法只接受以逗号分离的多个参数，但很多情况下我们需要传入一个信息量大数组，这个时候通过apply方法就可以简单的实现.
    
  
  

  

