# jQuery笔记  

## jquery基础知识
### 1.1 回顾前面js的痛点  

1. window.onload的事件覆盖问题，只能写一个。
2. 代码容错性差。
3. 浏览器兼容问题。
4. 书写繁琐。
5. 代码很乱。
6. 动画效果很难实现。  

### 1.2 jQuery解决问题  

​	jQuery解决上面js所遇到的痛点问题。  

### 1.3 jQuery的基本使用  

​	jQuery的基本形式有两种：

1. jquery-1.11.1.js
2. jquery-1.11.1.min.js

​	min：代表压缩版本，常在实际工程中使用，占用空间小。
正常版本没有压缩，便于学习，占用空间较大。

​	jQuery的版本问题：

1. 1.xxx版本 兼容IE6、7、8；
2. 2.xxx版本 不再兼容IE6、7、8；  

#### 1.3.1 引入文件    

​	1.首先把jQuery的源文件加入到工程项目中；
​	2.在页面中引用jQuery文件。  

```javascript
<script src="jquery-1.11.1.js"></script>    
```

​	jquery-1.11.1 百度CDN：

```  javascript
<script src=”http://libs.baidu.com/jquery/1.11.1/jquery.min.js”></script> 
```

​	jquery-2.1.1 百度CDN：

```  javascript
<script src=”http://libs.baidu.com/jquery/2.1.1/jquery.min.js”></script> 
```

​	需要注意的是，需要在用jQuery之前引用jQuery文件。先引用再使用。

####  1.3.2 入口函数  


``` javascript  
//1.
$(document).ready(function(){});

//2.
$(function(){});  
```


####  1.3.3 事件处理程序  

1.事件源  
js方式：`document.getElementById("id")`  
jquery方式：`$("#id")`    

2.事件  
js方式：`document.getElementById("id").onclick`  
jquery方式：`$("#id").click`  
jquery方式没有on;  
3.事件处理程序：  
js书写：`document.getElementById("id").onclick=function(){} `  
jquery书写：` $("#id").click(function(){}); `  


###  1.4 jQuery 详细介绍  

1. $ 符号的问题  

   jQuery 占用的两个变量：$ 和 jQuery.

2. js入口函数和jQuery入口函数的区别：  

   - js 的window.onload事件是等到所有内容，以及外部图片之类的文件加载完了才去执行。  
   - jQuery的入口函数是在所有的DOM节点都加载完以后就会去执行。  

###  1.5 JS创建对象  

三种方式：  

 	1. var obj = {};
 	2. var obj1 = new Object();  
 	3. var obj2 = Object.create();      

推荐使用第一种方式，第二种存在效率问题。   

### 1.6 jquery基本选择器  

jQuery的基本选择器：

| 符号                                                         | 说明 | 用法 |
| ------------------------------------------------------------ | ---- | ---- |
|`$("#demo")`| 选择id为demo的第一个元素 | `$("#demo").css("background","red");`   |
|`$(".item")`|  选择所有类名为item的元素  |  `$(".item").css("background","red") ` |
| `$("div")`|  选择所有标签名为div的元素  |  `$("div").css("background","red")`|
| `$("\*")`|  选择所有元素  | ` $("\*").css("background","red")`  |

### 1.7 jquery是什么  
jquery是JavaScript的一个库，把我们常用的一些功能进行封装，方便调用，提高开发效率。  
### 1.8 jquery的其他选择器  
####  1.8.1 层级选择器  
| 符号 | 说明 | 用法 |
| ---- | ---- | ---- |
| 空格 | 后代选择器 | `$("div span").css("background","red");` |
| >    | 子代选择器 | `$("div >span").css("background","red");` |
| +    | 紧邻选择器 | `$("div+p").css("background","red");` |
| ~    | 兄弟选择器 | `$("div ~p").css("background","red");` |

层级选择器选择了选择符后面的元素，比如div>p,是选择>后面的p元素。  

#### 1.8.2 过滤选择器  
基本过滤选择器：  
| 符号 | 说明 | 用法 |
|---- |---- |----|
| `:eq(index)` | 选择序号为index的第一个元素 | `$("li:eq(1)").css("background","red");` |
| `:gt(index)` | 选择序号大于index的元素 | `$("li:gt(2)").css("background","red");` |
| `:lt(index)` | 选择小于index的元素 |`$("li:lt(2)").css("background","red");` |
| `:odd` | 选择所有序号为奇数行的元素 |`$("li:odd").css("background","red");` |
| `:even` | 选择所有序号为偶数的元素 | `$("li:even").css("background","red");` |
|`:first` | 选择匹配第一个元素 | `$("li:first").css("background","red"); `|
| `:last` | 选择匹配最后一个元素 |`$("li:last").css("background","red");`|

属性选择器：  
|符号|说明|用法|
|----|----|----|
|`$("a[href]")`|选择所有包含href属性的元素  |`$(“a[href]”). css(“background”,”red”)` |
| `$("a[href='itcast']") `|选择href属性值为itcast的所有a标签 |`$(“a[href=’itcast’]”). css(“background”,”red”)` |
|`$("a[href!='baidu']") `|选择所有href属性不等于baidu的所有元素，包括没有href的元素 |`$(“a[href!=’baidu’]”). css(“background”,”red”)` |
|`$("a[href^='web']") `|选择所有以web开头的元素 |`$(“a[href^=’web’]”). css(“background”,”red”)` |
|`$("a[href$='cn']") `|选择所有以cn结尾的元素 |`$(“a[href$=’cn’]”). css(“background”,”red”) `|
|`$("a[href\*='i']") `|选择所有包含i这个字符的元素 |`$(“a[href\*=’i’]”). css(“background”,”red”)` |
|`$("a\[href]\[title='我']")` |选择所有符合指定属性规则的元素 |`$(“a\[href]\[title=’我’]”). css(“background”,”red”)` |

### 1.9 mouseover 事件和 mouseenter事件的区别     
mouseover/mouseout 事件，鼠标经过的时候会触发多次，每遇到一个子元素就会触发一次。  
mouseenter/mouseleave事件，鼠标经过的时候只会触发一次。  

### 1.10 DOM 对象和jquery对象相互转换  
jquery对象转换成DOM对象：  
方式一：` $("#btn")[0]`  
方式二：`$("#btn").get(0)`
DOM对象转换成jquery对象：  
`$(document) ` -> 把DOM对象转成jquery对象  
`var btn = document.getElementById("btn"); ` 
`btn    ->   $(btn);`  

## jquery操作DOM  
### 1.1 动画   
#### 1.1.1 基本效果 （显示和隐藏）  
``` javascript
$("div").show();//显示div  
$("div").hide();//隐藏div  
```
#### 1.1.2 滑动效果  
``` javascript
$("div").slideDown();//下拉显示  
$("div").slideUp();//上拉  
$("div").slideToggle();//上拉下拉切换
```

#### 1.1.3淡入淡出效果  
```javascript
$("div").fadeIn();//淡入
$("div").fadeOUt();//淡出
$("div").fadeToggle();//淡入淡出切换
$("div").fadeTo();//设置不透明度
```
#### 1.1.4 自定义动画  
```javascript
$("div").animate();//自定义动画
$("div").stop(); //结束动画
```

### 1.2 操作样式   
```javascript
$("div").css("background","blue");  //设置css参数 
$("div").addClass("color-red");  	//添加样式
$("div").removeClass("color-red")  	//移除样式
$("div").toggleClass("color-red")  	//切换样式
```
### 1.3 常用DOM操作  （属性、值、内容）  

```javascript
$("div").attr("name");	//获取name属性值
$("div").removeAttr("name");	//移除属性
$("input").val(function(i,v){});	//设置input的值

```

### 1.4 操作文档  
####  1.4.1 内部插入节点  
```javascript
$("div").append(node);	//在div内部的后面追加元素
node.appendTo("div");	//把node追加到div
$("div").prepend(node);	//在div内部的前面追加元素
node.prependTo($("div"))	//把node追加到div内部的前面
```
#### 1.4.2 外部插入节点  
```javascript
$("div").after(node);	//在div后面添加兄弟节点node
$("div").before(node);	//在div前面添加兄弟节点node
$("div").insertBefore(node);	//把div插入到node前面
$("div").insertAfter(node);		//把div追加到node后面
```

#### 1.4.3 删除节点  

```javascript
$("div").remove();	//删除选中的元素
$("div").empty();	//清空子元素
```

#### 1.4.4 复制节点  

```javascript
$("div").clone();	//复制节点
注：参数为true的话	，会把之前绑定的事件也复制一份。
```

#### 1.4.5 包裹节点  

```javascript
$("div").wrap(node);	//单个包裹
$("div").wrapAll(node);	//所有包裹在一个节点中
```

#### 1.4.6 替换节点  

```javascript
$("div").replaceWith(node);	//替换

```

### 1.5 操作元素  

####  1.5.1 获取元素的高和宽  

* height: $(selector).height(); //带参数设置，不带参数获取
* width: $(selector).width(); //带参数设置，不带参数获取
* innerHeight: //只能获取，内边距+内容的高度
* innerWidth: //只能获取，内边距+内容的宽度
* outerHeight://获取：内边距+内容+上下边框
* outerWidth://获取：内边距+内容+左右边框  

#### 1.5.2 元素坐标操作  

* offset() 获取或设置元素相对于文档的位置
  - 返回一个object，包含left 和top 属性，值是相对于document的位置。
  - 如果传入一个参数，则是对元素重新设置相对于document的位置。**传入参数必须包括：left和top属性。比如$(selector).offset({left:100,top150});**    
* position()获取相对于其最近的定位的父元素的位置。
  * 只能获取，不能设置。
  * 相对与其最近的**定位父元素** 。
  * 返回一个object，包含left 和top 属性。
* 元素的滚动
  * scrollLeft() 获取或者设置元素水平方向滚动的位置。
  * scrollTop() 获取或者设置窗口垂直方向滚动的位置。
  * scroll() 事件触发或者绑定滚动事件
    - scroll(handler)绑定滚动事件
    - scroll()触发滚动事件，如$(selector).scroll(fun(){});

### 1.6 事件绑定机制   

#### 1.6.1 简单事件绑定方法  

- .click(hander)  .click() //绑定事件或者触发 click事件
- .blur()  //失去焦点事件，同上
- .hover(mousein, mouseleave) //鼠标移入，移出
- mouseout： 当鼠标离开元素及它的子元素的时都会触发。
- mouseleave: 当鼠标离开自己时才会触发，子元素不触发。
- .dbclick() 双击
- change 改变,比如：文本框发送改变，下来列表发生改变等...
- focus 获得焦点
- keyup, keydown, keypress :  键盘键被按下。
- mousedown, mouseover

#### 1.6.2绑定事件的方法  

##### 1.bind方法  
不推荐，1.7以后的版本被on取代

- 语法格式：.bind(eventType,[eventData],handler);

- 参数说明：

  - eventType:事件类型
  - eventData:传递给事件响应方法的数据对象，可以省略
  - handler：事件响应方法
  - 事件响应方法中获取数据的方式：e.data;

- 例如：

  ```javascript
  $("p").bind("click", function(e){
          //事件响应方法
      });
  ```


##### 2.delegate方法  

推荐，性能高，支持动态创建的元素

- 语法格式：$(selector).delegate(selector,eventType,handler);

- 参数说明：

  - selector:子选择器
  - 第二个参数：事件类型
  - 第三个参数：事件响应方法

- 例如：

  ```javascript
  $(".parentBox").delegate("p", "click", function(){
          //为 .parentBox下面的所有的p标签绑定事件
      });
  ```

- 优势：效率较高。

##### 3. on方法  

最现代的方式，兼容zepto，强烈建议的方法

- jquery1.7版本以后，用on统一了所有事件的处理方法

- 语法格式：$(selector).on(events,selector,handler);

- 参数说明：

  - events:事件名
  - selector：子选择器
  - handler：事件处理方法

- 例如：

  ```javascript
  //绑定一个方法
      $( "#dataTable tbody tr" ).on( "click", function() {
        console.log( $( this ).text() );
      });
  
      //给子元素绑定事件
      $( "#dataTable tbody" ).on( "click", "tr", function() {
        console.log( $( this ).text() );
      });
  
      //绑定多个事件的方式
      $( "div.test" ).on({
        click: function() {
          $( this ).toggleClass( "active" );
        }, mouseenter: function() {
          $( this ).addClass( "inside" );
        }, mouseleave: function() {
          $( this ).removeClass( "inside" );
        }
      });
  ```


##### 4. one绑定一次事件的方法  

- 语法格式：.one(events,[data],handler);

- 例如：

  ```javascript
  $( "p" ).one( "click", function() {
        alert( $( this ).text() );
      });
  ```


#### 1.6.3 解绑事件  

##### 1.unbind方法  

- 在jquery1.7版本以后被on和off替代
- $(selector).unbind();  //解绑所有事件
- $(selector).unbind("click");  //解绑指定的click事件

##### 2.undelegate方法  

- $("p").undelegate();  //解绑所有的delegate事件
- $("p").undelegate("click");  //解绑指定的click事件

##### 3.off方法  

- $("p").off();//解绑所有事件

- $("p").off("click","**");//解绑所有的click事件，两个\*表示所有

- $("body").off("click","p",foo);

  ```javascript
  案例1：
      var foo = function() {
        // Code to handle some kind of event
      };     
      // ... Now foo will be called when paragraphs are clicked ...
      $( "body" ).on( "click", "p", foo );    
      // ... Foo will no longer be called.
      $( "body" ).off( "click", "p", foo );
  
      案例2：（了解）解绑命名空间的方式：
      var validate = function() {
        // Code to validate form entries
      };     
      // Delegate events under the ".validator" namespace
      $( "form" ).on( "click.validator", "button", validate );     
      $( "form" ).on( "keypress.validator", "input[type='text']", validate );  
      // Remove event handlers in the ".validator" namespace
      $( "form" ).off( ".validator" );
  ```


#### 1.6.4 触发事件  

- 简单事件触发：$(selector).click(); //触发 click事件

- trigger方法触发事件：$( "#foo" ).trigger( "click" );

- triggerHandler触发： 事件响应方法，不触发浏览器行为

  $( "input" ).triggerHandler( "focus" );

### 1.7 event对象  

- event.data            //传递的额外事件响应方法的额外参数
- event.currentTarget === this   //在事件响应方法中等同于this，当前Dom对象
- **event.target **         //事件触发源，不一定===this
- **event.pageX**         //The mouse position relative to the left edge of the document
- **event.pageY**
- **event.stopPropagation()**//阻止事件冒泡
- **e.preventDefault();**    //阻止默认行为
- event.type                 //事件类型：click，dbclick...
- event.which                //鼠标的按键类型：左1 中2 右3
- keydown : a,b,c
- event.keyCode           // code的c是大写

### 1.8 jquery其他补充    

- $()的几种常用用法：
  - $("id")选择某元素，返回jquery对象
  - $(this)将DOM对象转换为jquery对象
  - $("<div></div>")创建元素，返回值为jquery对象
  - $("function(){}"); 入口函数的简写方式
  - $(div).html()获取内容时，只返回匹配到的第一个元素的数据



