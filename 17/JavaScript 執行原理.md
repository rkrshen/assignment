Hoisting

        //作用域
        // － 作用域指的是一個變量的作用範圍

        // － 在ＪＳ終有兩種作用域
        //      1.全局作用域
        //         － 直接編寫在script標籤中的ＪＳ代碼，都在全局作用域
        //         － 在頁面打開時創建，在頁面關閉時銷毀
        //         － 在全局作用域中有一個全局對象window
        //            它代表一個瀏覽器的窗口，他游瀏覽器創建我們可以直接使用
        //         － 在全局作用域中我們創建的對象都最作為window對象的屬性保存
        //            我們創建的函數都最作為window對象的方法保存
        //         － 全局作用域中的變量都是全局變量，在頁面的任意部分都可以訪問到




        var a = 10;

        console.log(window.a);//10


        function fun() {
            console.log('ha');
        }
        fun();
        window.fun();//一樣的







        //變量的聲明提前
        //－使用var關鍵字的變量，會在所有代碼執行之前被聲明執行之前先聲明好(不會賦值)
        //－但是如果聲明變量時不使用var則變量不會被提前聲明

        //函數的聲明提前
        //－使用函數聲明形式創建的函數，會在所有代碼執行之前被創建
        //－所以我們可以在函數創建之前調用函數
        //－使用函數表達式創建的函數，不會被聲明提前




        //a = 123;

        var a = 123;

        console.log("a="+window.a);




        console.log("b="+window.b);

        var b = 123;//undefined
        //b = 123;//報錯



        var c;

        console.log("c="+window.c);

        c = 123;//undefined


        /////////////////////////

        fun();//執行
        //fun2();//報錯

        console.log(fun2);//undefined

        function fun() {
            console.log("1");
        }

        var fun2 = function () {
            console.log("2");
        }




        //作用域
        // － 作用域指的是一個變量的作用範圍

        // － 在ＪＳ終有兩種作用域
        //      2.函數作用域
        //         － 調用函數時創建函數作用域，函數執行完畢以後，函數作用域銷毀
        //         － 每調用一次就會創建一個新的函數作用域，他們之間是互相獨立的
        //         － 在函數作用域中可以訪問到全局變量，在全局作用域中無法訪問到局部作用域
        //            
        //         － 當在函數作用域中操作一個變量時，會先在自身作用域中尋找
        //            沒有的話才去上一級中尋找
        //         － 




        var a = 10;

        function fun() {
            console.log('ha');
        }
        fun();//函數作用域
        fun();//函數作用域
        fun();//函數作用域，各自獨立的


        function fun2() {
            console.log(a);
        }
        fun2();


Prototype



        //原型prototype
        //我們所創建的每一個函數，解析器都會向函數中添加一個prototype
        //每個都是獨一無二
        //console.log(MyClass.prototype == Person.prototype)
        //出來會是false
        //這個屬性對應著一個對象，也就是我們的原型對象



        function MyClass() {
            
        }

        //向MyClass添加屬性a
        MyClass.prototype.a = 123;
        //向MyClass添加一個方法
        MyClass.prototype.sayName = function () {
            alert('Cerise');
        }



        var mc1 = new MyClass();
        var mc2 = new MyClass();
        console.log(mc1.a);//123，與原型對象共用a
        
        console.log(mc1.__proto == mc2.__proto);//true

        mc1.a = "mc1的a";
        console.log(mc1.a);//"mc1的a"，自己的a

                //原型prototype
        //我們所創建的每一個函數，解析器都會向函數中添加一個prototype
        //每個都是獨一無二
        //console.log(MyClass.prototype == Person.prototype)
        //出來會是false
        //這個屬性對應著一個對象，也就是我們的原型對象



        function MyClass() {

        }

        //向MyClass添加屬性name
        MyClass.prototype.name = 'paul';
        // //向MyClass添加一個方法
        // MyClass.prototype.sayName = function () {
        //     alert('Cerise');
        // }



        var mc1 = new MyClass();
        var mc2 = new MyClass();
        console.log(mc1.name); //paul'


        //使用in檢查對象中是否含有某個屬性，如果對象中沒有但原型有，也會返回true
        console.log('name' in mc1); //true

        var t = mc1.hasOwnProperty('name');
        console.log(t); //false

        console.log(mc1.__proto__); //MyClass
        console.log(mc1.__proto__.__proto__); //object

        console.log(mc1.__proto__.__proto__.hasOwnProperty('hasOwnProperty')); //true
        //hasOwnProperty 是object對象中的屬性


Call Stack==> 以 Stack 資料結構為原理的程式執行方式


Execution Context 執行環境==>Global EC