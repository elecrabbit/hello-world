JavaScript中的函数变量作用域

## JS中的函数变量作用域问题  

示例代码：  

```javascript
<script>
    var a = 0;          //声明全局变量a     
    var b = 1;          //声明全局变量b
    var c = 2;          //声明全局变量c
    f1();               //进入函数f1();
    function f1() {
        var a = b = 9;  //声明了局部变量a,b还是全局变量
        var c = 8;      //声明局部变量c
        console.log(a); //局部变量a=9;
        console.log(b); //全局变量b被赋值9;
        console.log(c); //局部变量c=8;
    }
    console.log(c);     //全局变量c=2;
    console.log(b);     //全局变量b=9;
    console.log(a);     //全局变量a=0;
</script>
最后结果为：
9
9
8
2
9
0
```

- 只要是在`<script></script>`标签内定义的变量，都属于全局变量，不管是不是在同一对标签里出现。
- 函数内部先查找变量声明，如果变量没有声明则再去上一级里面查找，局部变量的值的改变并不影响全局变量的值。
- 如果变量没有找到声明则报错，如果变量有声明但是没有赋值则输出undefined。