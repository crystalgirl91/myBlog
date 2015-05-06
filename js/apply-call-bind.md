#apply and call and bind

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
  
###bind 语法：Function.prototype.bind(Object,params),

bind方法是ECMAScript5中的新方法。用于返回一个this值及参数已指定的新函数。

#####第一个参数Object : 
        var add = function(y){
            return this.x + y
        };
        var bindAdd = add.bind({"x":1});
        bindAdd(2);          ##输出3
        
上面的例子，首先声明一个函数add，在add上调用bind，传入的第一个参数Object为{"x":1},返回了一个新的函数并赋值给bindAdd，这个新函数bindAdd的执行上下文（this）将永远指向Object。所以输出3。

#####第二个参数Params : 
        var add = function(x,y){
            return x + y
        };
        var bindAdd = add.bind(null,1);
        bindAdd(2);          ##输出3

接着看这个例子，在add上调bind函数，传入的第一个参数为null，即,返回新函数的this值为null。传入的第二个参数Prames为1，
它绑定了新函数的参数，换句话说，每次调用新函数bindAdd，这个参数params（例子中的参数1）都会作为实参传入函数，而bindAdd自定义的参数（例子中的参数2）会依次追加在后面被传入函数。所以x为1，y为2，输出3。

#####注意:
    var add = function(arr,data){
        arr.push(data);
        return arr;
    };
    var bindAdd = add.bind(null,[]);
    bindAdd("hello");          ##输出["hello"]
    bindAdd("world");          ##输出["hello","world"]
    bindAdd("my");             ##输出["hello","world","my"]
    
接着看这个例子，调bind函数传入的第二个参数为一个数组，每次调用bindAdd方法时，bind的第二个参数传给了形参arr，自定义参数传给了形参data,继而这条数据被插入数组。这里需要注意的是第二次调用bindAdd方法时，输入结果是基于第一次的结果的，换句话说，第二次传给形参arr的数组不再bind中传入的那个空数组，而是第一次调用中被修改了的数组。所以综上，bind方法中的第二个参数，是为新函数绑定参数，而不是传参数。
        



    
  
  

  

