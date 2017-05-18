##  一. 普通对象与函数对象
     JavaScript 中，分为普通对象和函数对象，Object ，Function 是JS自带的函数对象。下面举例说明

     function f1(){};
     var f2 = function(){};
     var f3 = new Function('str','console.log(str)');

     var o1 = {};
     var o2 = new Object();
     var o3 = new f1();

     console.log(typeof Object); //function
     console.log(typeof Function); //function
     console.log(typeof o1); //object
     console.log(typeof o2); //object
     console.log(typeof o3); //object
     console.log(typeof f1); //function
     console.log(typeof f2); //function
     console.log(typeof f3); //function
	
  在上面的例子中 o1 o2 o3 为普通对象，f1 f2 f3 为函数对象。怎么区分，其实很简单，凡是通过 new Function() 创建的对象都是函数对象，其他的都是普通对象。f1,f2,归根结底都是通过 new Function()的方式进行创建的。function Object 也都是通过 New Function()创建的。
  

##  二、显式原型属性与隐式原型属性
   在JavaScript 中，每当定义一个对象（函数）的时候，对象中都会包含一些预定义的属性。
   每个函数function都有一个prototype属性，即显式原型属性，它是在定义函数时自动添加的, 默认值指向一个空Object对象
   每个实例对象都有一个__proto__属性，可称为隐式原型属性，它是在创建对象时自动添加的, 默认值为构造函数的prototype属性值
   对象的隐式原型的值为其对应构造函数的显式原型的值
   
##  三、原型链
   访问一个对象的属性时，先在基本属性中查找，如果没有，再沿着__proto__这条链向上找
   别名: 隐式原型链
   作用: 查找对象的属性(方法)
   
   
   
##  四、constructor
  原型对象prototype中都有个预定义的constructor属性，用来引用它的函数对象。这是一种循环引用
	person.prototype.constructor === person //true
	Function.prototype.constructor === Function //true
	Object.prototype.constructor === Object //true
