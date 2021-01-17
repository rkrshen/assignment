
        //非數值情況
        // - 對於非數值進行比較時，會將其轉會韋數字然後再比較
        // - 如果符號兩側的值都是字符串時，不會將其轉換為數字進行比較
        //          而會分別比較字符串裡面的Unicode編碼

        console.log(1 > true);//false 
        console.log(1 >= true);//true  她把true當成1
        console.log(1 >= "0");//true 

        console.log(10 >= null);//true 她把null當成0

        //任何值和NaN做任何比較都是false
        console.log(10 >= 'hello');//false 她把undefined當成NaN
        console.log(true > false);//true 


        //比較字符串的編碼
        console.log("1" < "5");//true 
        console.log("11" < "5");//true 

        console.log("a" > "b");//false
        console.log("a" < "b");//true 
        //比較字符編碼的時候是一位一位進行比較
        //如果兩位一樣，則比較下一位，可以借用他來對英文來進行排序
        console.log("abc" < "b");//true 
        //比較中文沒有意義

        //比較的是兩個字符串型的數字，可能會得到不可預期的結果
        //注意：在比較兩個字符串的數字時候，定要轉
        console.log("11483905948" < "5");//true 拿1和5的編碼比

                //注意：在比較兩個字符串的數字時候，定要轉型
                console.log("11483905948" < +"5");//false 用加號轉型
        //相等運算符用來比較兩個值是否相等
        //如果相等返回true,否則false


        //使用==來做運算
        // - 當使用==來比較兩個值時，如果值的類型不同，
        //      則會自動進行類型轉換，將其轉換為相同的類型
        //      然後再比較
        //不相等
        // - 不相等用來判斷兩個值是否不相等，不相等返回true，相等返回false
        // - 使用!=來做運算
        // - 不相等也會對變量進行自動的類型轉換，如果轉換相等他也會返回false


        // ===全等
        // - 用來判斷兩個值是否全等，不會做自動類型轉換
        //   如果兩個值類型不同，直接返回false

        // !==全等
        // - 用來判斷兩個值是否不全等，不會做自動類型轉換
        //   如果兩個值類型不同，直接返回true

        console.log(1 == 1);//true

        var a = 10;
        console.log(a == 1);//false a的值10

        console.log("1" == 1);//true
        console.log(true == 1);//true

        console.log(true == '1');//true 都轉成數字
        console.log(true == 'hello');//false

        console.log(null == 0);//false

        //undefined 衍生自 null 
        //所以這兩個值做相等判斷時，都會返回true
        console.log(null == undefined);//true


        //NaN不和任何值相等，也包括他本身

        console.log(NaN == NaN);//false


        //要判斷一個值是否是NaN
        //可以通過isNaN()函數來判斷
        var b = NaN
        console.log(b == NaN);//false
        console.log(isNaN(b));//true


        console.log(1 != "1");//false


        console.log(1 === "1");//false
        console.log(null === undefined);//false


        //=
        //  可以將右側的值賦給左側變量
        //+= 
        //  a += 5等價於a = a + 5
        //*= 
        //  a *= 5等價於a = a * 5
        // /= 
        //  a /= 5等價於a = a / 5

        // %= 
        //  a %= 5等價於a = a % 5


        var a = 10;

        //a = a + 5;
        a += 5;

        console.log("a = "+a);

        //相等運算符用來比較兩個值是否相等
        //如果相等返回true,否則false


        //使用==來做運算
        // - 當使用==來比較兩個值時，如果值的類型不同，
        //      則會自動進行類型轉換，將其轉換為相同的類型
        //      然後再比較
        //不相等
        // - 不相等用來判斷兩個值是否不相等，不相等返回true，相等返回false
        // - 使用!=來做運算
        // - 不相等也會對變量進行自動的類型轉換，如果轉換相等他也會返回false


        // ===全等
        // - 用來判斷兩個值是否全等，不會做自動類型轉換
        //   如果兩個值類型不同，直接返回false

        // !==全等
        // - 用來判斷兩個值是否不全等，不會做自動類型轉換
        //   如果兩個值類型不同，直接返回true

        console.log(1 == 1);//true

        var a = 10;
        console.log(a == 1);//false a的值10

        console.log("1" == 1);//true
        console.log(true == 1);//true

        console.log(true == '1');//true 都轉成數字
        console.log(true == 'hello');//false

        console.log(null == 0);//false

        //undefined 衍生自 null 
        //所以這兩個值做相等判斷時，都會返回true
        console.log(null == undefined);//true


        //NaN不和任何值相等，也包括他本身

        console.log(NaN == NaN);//false


        //要判斷一個值是否是NaN
        //可以通過isNaN()函數來判斷
        var b = NaN
        console.log(b == NaN);//false
        console.log(isNaN(b));//true


        console.log(1 != "1");//false


        console.log(1 === "1");//false
        console.log(null === undefined);//false
        //條件運算符也叫做三元運算符
        //語法
        //   條件表達式 ? 語句1:語句2

        // - 執行的流程       
        //      條件運算符在執行時，首先對條件表達式進行求值
        //          如果該值為true，則執行語句1，並返回執行結果
        //          如果該值為false，則執行語句2，並返回執行結果

        //      如果條件表達式的求值結果不是布爾值
        //      會將其轉換為布爾值再做運算
        true ? alert('a'):alert('b');



        var a = 20;
        var b = 30;
        var c = 50;
        a > b ? alert('a大'):alert('b大');



        var max = a > b ? a : b;
        console.log('max='+max);


        //獲取a b c 中的最大值
        max = max > c ? max : c;
        console.log('max='+max);


        //這種寫法不推薦
        //不方便閱讀
        var max2 = a > b ? (a > c ? a : c) : (b > c ? b : c);

        console.log('max2='+max2);


        "hello" ? alert('語句1'):alert('語句2');//'語句1'
        "" ? alert('語句1'):alert('語句2');//'語句2'
        // , 運算符
        // 使用, 可以分割多個語句,一般來說可以在聲明多個變量時使用,
        
        
        //同時聲明多個變量並且賦值
        // var a;
        // var b; 
        // var c;
        // var a, b, c;
        var a = 1, b = 2, c = 3;

        alert(b);

        //ＪＳ當中也有優先級
        // 例如：先乘除後加減
        //ＪＳ有優先級的表
        //  表中月上面表示優先級越高，優先級越高越優先計算
        //  如果優先及一樣高，則從左至右
        //  優先級不清楚可以使用（）來改變層級

        //
        var result = 1 || 2 && 3;//1

        //&& > || ,則 2 && 3 返回 3，1 || 3 則返回1;



參數 Parameter 
引數 Argument

function fun1 (a, b) {
    return a+b;
}
var c = 10;
var d = 20;
console.log( fun1(c,d) );

==>30

Function 參數帶入 Function

function f1(i, ff2) { // newFunction 為 fun1() 的參數
    return i + ff2;
}
function f2(x) {
    return x * 2;
}
console.log(f1(5, f2(10))); 
==>25



charCodeAt(str) 
取出字元的 ASCII 碼
String.fromCharCode(num) 
將 ASCII 碼轉成字元

