# proto
        —> 创建对象有几种方法—> 原型，构造函数，对象实例，原型链—> instanceof的原理—> new运算符
        创建对象的几种方法：var 01 = {name: ‘o1’};
                        var 011 = new Object({name: ‘o11’});
                        构造函数：
                        var M = function(){this.name = ‘m’;}
                        var o2 = new M();
                        var P = {name: ‘o3'}
                        var o3 = Object.create(P);
        构造函数—new—>实例对象—__proto__—>原型对象构造函数—prototype—>原型对象构造函数<—constructor--原型对象
        new运算符：Step1： 一个新对象被创建，它继承自foo.prototype==>
        Step2： 构造函数foo被执行，执行的时候，相应的传参会被传入，同时上下文（this）会被指定为这个新实例。new foo等同于new foo()，只能用在不传递任何参数的情况下==>
        Step3: （如果构造函数返回了一个“对象”，那么这个对象会取代整个new出来的结果。如果构造函数没有返回对象，）
        那么new出来的结果为步骤1创建的对象。
        new的代码：var new2 = function(func) {var o = Object.create(func.prototype);var k = func.call(o);If(typeof k === ‘object’ ) {return k;} else {return o;}
