<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<!--25.已知函数 fn 执行需要 3 个参数。请实现函数 partial，调用之后满足如下条件：
1、返回一个函数 result，该函数接受一个参数
2、执行 result(str3) ，返回的结果与 fn(str1, str2, str3) 一致-->
<script>
    //方法一
    function partial(fn, str1, str2) {
    function result(str3) {
       return fn.call(this,str1,str2,str3);
    }
        return result;
    }
</script>
<script>
    //方法二
    function partial(fn,str1,str2) {
        function result(srt3) {
            return fn.apply(this,[str1,str2,srt3]);
        }
        return result;
    }
</script>
<script>
    //方法三
    function partial(fn, str1, str2) {
       return function (str3) {     //匿名函数
           return fn(str1,str2,str3);
       }
    }
</script>

<!--26.函数 useArguments 可以接收 1 个及以上的参数。
请实现函数 useArguments，返回所有调用参数相加后的结果。本题的测试参数全部为 Number 类型，不需考虑参数转换。-->
<script>
    //方法一
    function useArguments() {
      var sum =0;
      for (var i =0;i<arguments.length;i++){//arguments.length获取参数个数
         sum+=arguments[i];//循环求和
      }
      return sum;
    }
</script>
<script>
    //方法二
    function useArguments() {
     var arr=Array.prototype.slice.call(arguments);//将arguments转化为数组
     return eval(arr.join("+"));
    }

</script>

<!--27.实现函数 callIt，调用之后满足如下条件
1、返回的结果为调用 fn 之后的结果
2、fn 的调用参数为 callIt 的第一个参数之后的全部参数-->
<script>
    //方法一
    function callIt(fn) {
        var trueArray=Array.prototype.slice.call(arguments);//将arguments转化为数组
        var x=trueArray.slice(1);//截取第一个参数之后的全部参数
        var result =fn.apply(this,x);
        return result;
    }
</script>
<script>
    //方法二
    function callIt(fn) {
      var args=[];
       for (i=1;i<arguments.length;i++){//要求“fn 的调用参数为 callIt 的第一个参数之后的全部参数 ”
           args.push(arguments[i]);//fn(args)的传入的参数是一个数组，而apply(null,args)会把args数组里的元素依次传入做为参数
       }
       var result =fn.apply(null,args);
       return result;
    }
</script>

<!--28.实现函数 partialUsingArguments，调用之后满足如下条件：
1、返回一个函数 result
2、调用 result 之后，返回的结果与调用函数 fn 的结果一致
3、fn 的调用参数为 partialUsingArguments 的第一个参数之后的全部参数以及 result 的调用参数-->
<script>
    //方法一
    function partialUsingArguments(fn) {
    var args=Array.prototype.slice.call(arguments,1);
    var result=function () {
     return fn.apply(null,args.concat([].slice.call(arguments)));
    };
    return result;
    }
</script>
<script>
    //方法二
    function partialUsingArguments(fn) {
     var args=Array.prototype.slice.call(arguments,1);
      args.unshift(null);
      return fn.bind.apply(fn,args);
    }
</script>

<!--29.已知 fn 为一个预定义函数，实现函数 curryIt，调用之后满足如下条件：
1、返回一个函数 a，a 的 length 属性值为 1（即显式声明 a 接收一个参数）
2、调用 a 之后，返回一个函数 b, b 的 length 属性值为 1
3、调用 b 之后，返回一个函数 c, c 的 length 属性值为 1
4、调用 c 之后，返回的结果与调用 fn 的返回值一致
5、fn 的参数依次为函数 a, b, c 的调用参数-->
<script>
    /*柯里化是把接受多个参数的函数变换成接受一个单一参数(最初函数的第一个参数)的函数，并且返回接受余下的参数且返回结果的新函数的技术。
    * 题目意思是将预定义的函数参数传入curryIt中，当参数全部传入之后，就执行预定义函数。*/
    //方法一
    function curryIt(fn) {
    var length =fn.length;//fn.lengrh获取fn函数的参数个数
    var args=[];//声明一个空数组去存放参数
    var result=function (arg) {//返回一个匿名函数接受参数并执行
        args.push(arg);//将curryIt中括号中的参数放入数组
        length--;
     if (length<=0){
        return fn.apply(this,args);
     }else {
         return result;
     }
    };
    return result;
    }
</script>
<script>
    //方法二
    function curryIt(fn) {
     var arr=[];x=fn.length;
    return function (m) {
        arr.push(m);
        //arguments主要用途保存函数参数，它有一个callee属性，该属性指向拥有arguments对象的函数
        return arr.length<x?arguments.callee: fn.apply(null,arr);//?表判断
    }
    }
</script>

<!--30.返回参数 a 和 b 的逻辑或运算结果
或运算符“||”的运算规则是：如果第一个运算子的布尔值为true，则返回第一个运算子的值，且不再对第二个运算子求值；
如果第一个运算子的布尔值为false，则返回第二个运算子的值。-->
<script>
    function or(a, b) {
        return a||b;
    }
</script>
</body>
</html>
