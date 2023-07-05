#                                            CSS盒子模型

## 一、认识盒子模型

![image-20230421151414851](../../../Coderwhy/pic/image-20230421151414851.png)

### 1、盒子模型（Box Model）

可以把HTML每一个元素看出一个个的盒子，可以具备这4个属性

![image-20230421151714822](../../../Coderwhy/pic/image-20230421151714822.png)

#### （1）内容（content）

​	元素的内容width/height

#### （2）内边距（padding）

​	元素和内容之间的间距

#### （3）边框（border）

​	元素自己的边框

#### （4）外边距（margin）

​	元素和其他元素之间的间距

### 2、盒子模型的四边

因为盒子有四边, 所以margin/padding/border都包括top/right/bottom/left四个边:

![image-20230421152004970](../../../Coderwhy/pic/image-20230421152004970.png)

在浏览器的开发工具中

![image-20230421152026144](../../../Coderwhy/pic/image-20230421152026144.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      width: 100px;
      height: 100px;
      background-color: #f00;
      padding: 0%;
      border: solid;

    }
  </style>
</head>
<body>
  <div class="box">我是Box</div>
</body>
</html>
```



## 二、内容width/height

### 1、设置内容

设置内容是通过宽度和高度设置的:

- 宽度设置: width

- 高度设置: height

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* content */
    .box {
      width:200px;
      height:200px;
      background-color:#f00
    }
  </style>
</head>
<body>
  <div class="box"></div>
</body>
</html>
```



注意: 对于行内级非替换元素来说, 设置宽高是无效的!

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      background-color: #f00;

      /* width 默认是auto */
      /*浏览器默认是auto*/
      width: auto;

      /* width: 100%; */

    }

    .title {
      /* 行内级：包裹内容 */
      display: inline-block;
      width: auto;
    }

    img {
      width: auto;
      width: 200px;
    }
  </style>
</head>
<body>
  <div class="box">我是box</div>
  <span class="title">我是span元素</span>
  <img src="../images/gouwujie01.jpg" alt="">
</body>
</html>
```



### 2、属性

**另外我们还可以设置如下属性:**

- min-width：最小宽度，无论内容多少，宽度都大于或等于min-width
- max-width：最大宽度，无论内容多少，宽度都小于或等于max-width
- 移动端适配时, 可以设置最大宽度和最小宽度

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body {
      /* inline-level boxs  */
      /* text-align: center; */
    }
      
    .home {
      height: 2000px;
      background-color: #f00;

      /* 最大的宽度 */
      max-width: 750px;

      /* 最小的宽度 */
      min-width: 500px;

      /* 块级元素居中 */
      margin: 0  auto;
    }
      
  </style>
</head>
<body>
  <div class="home"></div>
</body>
</html>
```



### 3、不常用属性

**下面两个属性不常用:**

- min-height：最小高度，无论内容多少，高度都大于或等于min-height

- max-height：最大高度，无论内容多少，高度都小于或等于max-height



## 三、内边距padding

### 1、作用

padding属性用于设置盒子的内边距, 通常用于设置边框和内容之间的间距;

### 2、padding取值

padding包括四个方向, 所以有如下的取值:

- padding-top：上内边距

- padding-right：右内边距

- padding-bottom：下内边距

- padding-left：左内边距

### 3、padding缩写

padding单独编写是一个缩写属性

- padding-top、padding-right、padding-bottom、padding-left的简写属性

- padding缩写属性是从零点钟方向开始, 沿着顺时针转动的, 也就是上右下左;



### 3、padding其他值

padding并非必须是四个值, 也可以有其他值

![image-20230421153347501](../../../Coderwhy/pic/image-20230421153347501.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      /* 设置一个红色的实体边框 */
      border: 1px solid red;
      display: inline-block;

      /* line-height */
      /* line-height: 36px; */

      /* 内边距：padding */
      /* padding-top: 10px;
      padding-right: 20px;
      padding-bottom: 40px;
      padding-left: 40px; */

      /* 等价于：缩写属性 */
      /* padding: 10px 20px 30px 40px; */

      /* 其他值的情况 */
      /* 3个值 */
      padding: 10px 20px 30px;  /*left =  right*/
      /* 2个值 */
      padding: 10px 20px;  /* left = right bootom = top*/
      /* 1个值 */
      padding: 10px;  /*四个方向都一样*/
    }
  </style>
</head>
<body>
  <div class="box">我是box</div>
</body>
</html>
```



## 四、边框/圆角border 

### 1、作用

border用于设置盒子的边框:

### 2、边框得特殊属性

边框相对于content/padding/margin来说特殊一些:

- 边框具备宽度width;

- 边框具备样式style;

- 边框具备颜色color;

### 3、设置边框的方式

- 边框宽度	
  - border-top-width、border-right-width、border-bottom-width、border-left-width
  - border-width是上面4个属性的简写属性

- 边框颜色
  - border-top-color、border-right-color、border-bottom-color、border-left-color
  - border-color是上面4个属性的简写属性

- 边框样式
  - border-top-style、border-right-style、border-bottom-style、border-left-style
  - border-style是上面4个属性的简写属性

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      display: inline-block;
      width: 300px;
      height: 300px;

      /* width */
      /* border-top-width: 10px;
      border-right-width: 20px;
      border-bottom-width: 30px;
      border-left-width: 40px;  */
      /* border-width: 10px 20px 30px 40px; */

      /* style */
      /* border-top-style: solid;
      border-right-style: dashed;
      border-bottom-style: groove;
      border-left-style: ridge; */
      /* border-style: solid dashed groove ridge; */

      /* color */
      /* border-top-color: red;
      border-right-color: blue;
      border-bottom-color: green;
      border-left-color: orange; */
      /* border-color: red blue green orange; */

      /* 总缩写属性 */
      border: 10px solid red ;
    }
  </style>
</head>
<body>
  <div class="box">我是box</div>
</body>
</html>
```



### 4、边框的样式设置值

边框的样式有很多, 我们可以了解如下的几个: 

- groove：凹槽, 沟槽, 边框看上去好象是雕刻在画布之内

- ridge：山脊, 和grove相反，边框看上去好象是从画布中凸出来

![image-20230421153837636](../../../Coderwhy/pic/image-20230421153837636.png)

### 5、同时设置的方式

- 如果我们相对某一边同时设置 宽度 样式 颜色, 可以进行如下设置: 
  - border-top
  - border-right
  - border-bottom
  - border-left
  - border：统一设置4个方向的边框

- 边框颜色、宽度、样式的编写顺序任意

  ![image-20230421154134285](../../../Coderwhy/pic/image-20230421154134285.png)

### 6、圆角 – border-radius

- border-radius用于设置盒子的圆角
- border-radius常见的值
  - 数值: 通常用来设置小的圆角, 比如6px;
  - 百分比: 通常用来设置一定的弧度或者圆形;



### 7、border-radius补充

- border-radius事实上是一个缩写属性:
  - 将这四个属性 border-top-left-radius、border-top-right-radius、border-bottom-right-radius，和 border-bottom-left-radius 简写为一个属性。

- 开发中比较少见一个个圆角设置;

- 如果一个元素是正方形, 设置border-radius大于或等于50%时，就会变成一个圆
  - ![image-20230421155041338](../../../Coderwhy/pic/image-20230421155041338.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>

    div {
      width: 180px;
      height: 100px;
      background-color: #f00;

      border: 10px solid green;
    }

    .box {
      /* 设置圆角 */
      /* 设置具体的数值 */
      /* border-radius: 20px; */
      /* 设置百分比 */
      /* 百分比相对于谁, 了解即可 */
      border-radius: 10%;
    }

    .content {
      border-radius: 20px;
    }

    .home {
      width: 100px;
      height: 100px;
      border: 10px solid red;
      background-color: #0f0;

      border-radius: 50%;
    }
  </style>
</head>
<body>
  
  <div class="box"></div>
  <div class="content"></div>


  <div class="home"></div>

</body>
</html>
```



## 五、外边距margin

### 1、作用

margin属性用于设置盒子的外边距, 通常用于元素和元素之间的间距;

### 2、margin取值

margin包括四个方向, 所以有如下的取值:

- margin-top：上内边距

- margin-right：右内边距

- margin-bottom：下内边距

- margin-left：左内边距

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* 暂时解决方案 */
    body {
      font-size: 0;
    }

    .box {
      display: inline-block;
      width: 100px;
      height: 100px;
      background-color: #f00;

      /* margin-bottom: 30px; */
      /* margin-right: 30px; */
    }
    .container {
      display: inline-block;
      width: 100px;
      height: 100px;
      background-color: #0f0;

      /* margin-top: 30px; */
      /* margin-left: 30px; */

      /* 缩写属性 */
      /* margin: 10px 20px;  */  /*这个的话左边div下沉了*/
      margin: 0 20px;
    }
  </style>
</head>
<body>
  <div class="box"></div>

  <div class="container"></div>
</body>
</html>
```



### 3、margin缩写属性

margin单独编写是一个缩写属性

- argin-top、margin-right、margin-bottom、margin-left的简写属性

- margin缩写属性是从零点钟方向开始, 沿着顺时针转动的, 也就是上右下左;
- margin也并非必须是四个值, 也可以有其他值;



### 4、margin的其他值

![image-20230421165346374](../../../Coderwhy/pic/image-20230421165346374.png)



### 5、上下margin的传递

- margin-top传递
  - 如果块级元素的顶部线和父元素的顶部线重叠，那么这个块级元素的margin-top值会传递给父元素

- margin-bottom传递
  - 如果块级元素的底部线和父元素的底部线重写，并且父元素的高度是auto，那么这个块级元素的margin-bottom值会传递给父元素

- 如何防止出现传递问题？
  - 给父元素设置padding-top\padding-bottom
  - 给父元素设置border
  - 触发BFC: 设置overflow为auto

- 建议
  - margin一般是用来设置兄弟元素之间的间距
  - padding一般是用来设置父子元素之间的间距



盒子模型-margin-bottom传递(了解)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      width: 300px;
      /* height: 300px;  不会传递，auto情况会传递 */
      height: auto;
      background-color: #f00;
    }

    .container {
      width: 100px;
      height: 100px;
      background-color: #0f0;

      margin-bottom: 100px;
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="container">
    </div>
  </div>

  <div>哈哈哈哈啊</div>
</body>
</html>
```



盒子模型-margin的传递

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      width: 300px;
      height: 300px;
      background-color: #f00;

      /* 增加border则不会传递,下面代码逐渐优化 */
      /* border: 1px solid #000; */
      /* border: 1px solid transparent; */

      /* border: 1px solid rgba(0, 0, 0, 0);  同上面的transparent */
      /* border: 0 solid transparent; 不能设置为0   */

      /* 触发box的BFC */
      overflow: auto;
    }

    .container {
      width: 100px;
      height: 100px;
      background-color: #0f0;

      /* 左右是不会传递的 */
      /* margin-left: 30px; */

      /* 传递给了box，box就相对于div设置了 */
      margin-top: 100px;
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="container">

    </div>
  </div>
</body>
</html>
```



### 6、上下margin的折叠

- 垂直方向上相邻的2个margin（margin-top、margin-bottom）有可能会合并为1个margin，这种现象叫做collapse（折叠）

- 水平方向上的margin（margin-left、margin-right）永远不会collapse

- 折叠后最终值的计算规则
  - 两个值进行比较，取较大的值

- 如何防止margin collapse？
  - 只设置其中一个元素的margin

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box1 {
      height: 100px;
      background-color: #f00;

      margin-bottom: 30px;
    }

    .box2 {
      height: 100px;
      background-color: #0f0;

      margin-top: 50px;
    }
    /* collapse取最大值max(30,50) */
    
  </style>
</head>

<body>

  <div class="box1"></div>
  <div class="box2"></div>

</body>
</html>
```



### 7、上下margin折叠的情况

- 两个兄弟块级元素之间上下margin的折叠

- 父子块级元素之间margin的折叠

![image-20230421165905810](../../../Coderwhy/pic/image-20230421165905810.png)



块级元素的水平居中问题

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body {
      margin: 0;
      padding: 0;

      /* inline-level box */
      /* 行内级别：行内非替换元素span/a 行内替换元素  img input inline-block */
      /* text-align: center; */
    }

    .container {
      width: 800px;
      height: 150px;
      background-color: #0f0;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: #f00;

      /* 块级元素block box width =width + padding + border  + margin */
      /* display: inline-block; */

       /*0表示上下为0，左右为auto*/
      margin: 0 auto;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="box"></div>
  </div>
</body>
</html>
```

**块级元素水平居中**

![image-20230419224559807](../../../Coderwhy/pic/image-20230419224559807.png)

块级元素的水平居中问题margin-auto

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body {
      margin: 0;
      padding: 0;

      /* inline-level box */
      /* 行内级别：行内非替换元素span/a 行内替换元素  img input inline-block */
      /* text-align: center; */
    }

    .container {
      width: 800px;
      height: 150px;
      background-color: #0f0;
    }

    .box {
      /*div独占一行，设置了宽度，则margin-left = 0 ，box占了width = 100px, 则将独占一行的剩余分配给margin-right*/
      /*上面问题解决： margin-left和right设置为auto*/
      width: 100px;
      height: 100px;
      background-color: #f00;

      /* 块级元素block box width =width + padding + border  + margin */
      /* display: inline-block; */

      /*margin两个属性：上下是0，左右是auto*/
      margin: 0 auto;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="box"></div>
  </div>
</body>
</html>
```



### 8、外轮廓 - outline

- outline表示元素的外轮廓
  - 不占用空间
  - 默认显示在border的外面

- outline相关属性有
  - outline-width: 外轮廓的宽度
  - outline-style：取值跟border的样式一样，比如solid、dotted等
  - outline-color: 外轮廓的颜色
  - outline：outline-width、outline-style、outline-color的简写属性，跟border用法类似

- 应用实例
  - 去除a元素、input元素的focus轮廓效果

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      width: 100px;
      height: 100px;
      background-color: red;
      
      border: 50px solid orange;
      padding: 30px;

      /* 外轮廓 */
      outline: 10px solid #0f0;
    }

    /* a color: red lvlha active hover 都设置，所以下面伪类也可以设置 */
    a {
      /* a元素是行内级元素，设置margin效果无效 */
      margin-top: 10px;
      display: inline-block;

      /* 不添加的话，tab选中百度一下会有一个默认的外边框 */
      outline: none;
    }

    /* 伪类 */
    /* a::focus {
      outline: none;
    } */

    input {
      outline: none;
    }
  </style>
</head>
<body>
  <div class="box"></div>

  <a href="#">百度一下</a>


  <input type="text">
</body>
</html>
```



## 六、盒子和文字阴影

### 1、盒子阴影 – box-shadow

* box-shadow属性可以设置一个或者多个阴影
  * 每个阴影用<shadow>表示
  * 多个阴影之间用逗号,隔开，从前到后叠加
* <shadow>的常见格式如下
  * <img src="../../../Coderwhy/pic/image-20230521203611438.png" alt="image-20230521203611438" style="zoom:80%;" />
  * 第1个<length>：offset-x, 水平方向的偏移，正数往右偏移
  * 第2个<length>：offset-y, 垂直方向的偏移，正数往下偏移
  * 第3个<length>：blur-radius, 模糊半径
  * 第4个<length>：spread-radius, 延伸半径
  * <color>：阴影的颜色，如果没有设置，就跟随color属性的颜色
  *  inset：外框阴影变成内框阴影
* 盒子阴影 – 在线查看
  * [查看盒子阴影连接](https://html-css-js.com/css/generator/box-shadow/)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      height: 100px;
      width: 100px;
      background-color: red;
      /* 
      分别是x轴offset，y轴offset，模糊度，向四周增加模糊度 颜色属性 
      insert 表示向内添加阴影
      */
      
      /* box-shadow: 5px 5px 10px 10px orange inset; */

      /*阴影的叠加*/
      box-shadow: 5px 5px 10px 10px orange inset,5px 5px;
    }
  </style>
</head>
<body>
  <div class="box"></div>
</body>
</html>
```



### 2、文字阴影 - text-shadow

- text-shadow用法类似于box-shadow，用于给文字添加阴影效果
- <shadow>的常见格式如下
  - ![image-20230521203944375](../../../Coderwhy/pic/image-20230521203944375.png)
  - 相当于box-shadow, 它没有spread-radius的值;
- [我们可以通过一个网站测试文字的阴影](https://html-css-js.com/css/generator/box-shadow/)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      font-size: 50px;
      font-weight: 700;

      /*没有扩展和向内shadow*/
      text-shadow: 5px 5px 5px orange, 10px 10px 5px blue,5px 5px 10px green;
    }
  </style>
</head>
<body>
  <div class="box">Hello ZKYAAA</div>
</body>
</html>
```



### 3、行内非替换元素的特殊性

- 以下属性对行内级非替换元素不起作用
  - width、height、margin-top、margin-bottom

* 以下属性对行内级非替换元素的效果比较特殊
  * padding-top、padding-bottom、上下方向的border

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .content {
      background-color: #f00;
      color: white;

      /* 内容：width/height 不生效 */
      width: 300px;
      height: 300px;

      /* 内边距：padding */
      /* 特殊：上下会被撑起来，但是不占据空间 */
      /* padding: 50px; */

      /* 边框：border */
      /* 特殊：上下会被撑起来，但是不占据空间 */
      /* border: 50px solid orange; */

      /*外边距： margin */
      /* 特殊：上下的margin不生效 */
      margin: 50px;
    }
  </style>
</head>
<body>
  <span class="content">
    我是span内容，哈哈哈
  </span>
  aaaaa
  <!-- padding的上下padding是不占空间的 -->
  <div>
    bbbb
  </div>
</body>
</html>
```

背景和前景色设置的是哪些

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* 
      1> 背景色有没有设置到border下面(有设置)
      2> 前景色会在border没有设置颜色的情况下, 显示出来color颜色
    */
    .box {
      width: 100px;
      height: 100px;
      background-color: #f00;
      color: orange;
      padding: 30px;
      border: 10px solid;
    }
  </style>
</head>
<body>
  
  <div class="box"></div>

</body>
</html>
```



## 七、box-sizing

### 1、CSS属性 - box-sizing

* box-sizing用来设置盒子模型中宽高的行为

* content-box
  
  * padding、border都布置在width、height外边
  
* border-box
  
* padding、border都布置在width、height里边
  
* box-sizing: content-box
  * 元素的实际占用宽度 = border + padding + width
  * 元素的实际占用高度 = border + padding + height
  * ![image-20230521213834303](../../../Coderwhy/pic/image-20230521213834303.png)
  
* box-sizing: border-box
  * 元素的实际占用宽度 = width
  * 元素的实际占用高度 = height 
  * ![image-20230521213914011](../../../Coderwhy/pic/image-20230521213914011.png)
  
* IE盒子模型

  * W3C标准盒子模型
    * ![image-20230521214025833](../../../Coderwhy/pic/image-20230521214025833.png)
  * IE盒子模型（IE8以下浏览器）
    * ![image-20230521214046618](../../../Coderwhy/pic/image-20230521214046618.png)

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
      .box1 {
        box-sizing : content-box;
        width: 100px;
        height: 100px;
        background-color: #f00;
  
        padding: 30px;
        border: 10px solid orange;
      }
  
      .box2 {
        box-sizing: border-box;
        width: 100px;
        height: 100px;
        background-color: #f00;
  
        padding: 30px;
        border: 10px solid blue;
      }
    </style>
  </head>
  <body>
    <div class="box1"></div>
    <div class="box2"></div>
  </body>
  </html>
  ```

  效果展示：

  ![image-20230521214435517](../../../Coderwhy/pic/image-20230521214435517.png)

  



### 2、元素的水平居中方案

* 在一些需求中，需要元素在父元素中水平居中显示（父元素一般都是块级元素、inline-block）
* 行内级元素(包括inline-block元素)
  * 水平居中：在父元素中设置text-align: center

* 块级元素
  * 水平居中：margin: 0 auto



### 3、案例练习

#### （1）盒子模型练习-案例01-京东按钮

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="./css/reset.css">
  <style>
    .btn {
       /* 先全局后局部 */
       display: inline-block;

       width: 70px;
       height: 25px;
       line-height: 25px;

       /* 水平和垂直居中 */
       line-height: 25px;

       /* 内容居中 */
       text-align: center;

       border-radius: 13px;
    }

    /* a的样式 */
    .new {
      background-color: #e1251b;
      color: #fff;
    }

    .vip {
      background-color: #363634;
      color: #e5d790;
    }
  </style>
</head>
<body>
  <!-- 新人福利 -->
  <a class="btn new" href="https://xinren.jd.com/?channel=99#/home" target="_blank">新人福利</a>
  <a class="btn vip" href="https://passport.jd.com/new/login.aspx?ReturnUrl=https%3A%2F%2Fplus.jd.com%2Findex%3Fflow_system%3Dappicon%26flow_entrance%3Dappicon3%26flow_channel%3Dpc" target="_blank">PLUS会员</a>
</body>
</html>
```

```css
/* a的重置 */
a {
  text-decoration: none;
  color: #333;
  font-size: 14px;
}
```

![image-20230521221838866](../../../Coderwhy/pic/image-20230521221838866.png)

#### （2）盒子模型练习-案例02-京东小米手机

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="./css/reset.css">
  <style>
    body {
      text-align: center;
    }
    
    .item {
      display: inline-block;
      width: 234px;
      height: 300px;
      padding: 20px 10px;

      text-align: center;
      
      background-color: #fff;
      box-sizing: border-box;
    }
 
    .item:hover {
      box-shadow:  0 2px 20px 5px rgba(0, 0, 0, .1)
    }

    .item img {
      width: 160px;
      height: 160px;
    }

    .item .title {
      margin-top: 14px;
    }

    .item .desc{
      color: #999;
      margin-top: 8px;

      /* 单行显示省略号 */
      white-space: nowrap;
      /* 超出部分隐藏 */
      overflow: hidden;
      /* 三个点 */
      text-overflow: ellipsis;
    }
    .item .price {
      margin-top: 20px;
      font-size: 14px;
    }

    .item .new-price {
      color: #ff6700;
    }
    
    .item .old-price {
      color: #999;
      text-decoration: line-through;
    }

  </style>
</head>
<body>
  <a class="item" href="https://www.mi.com/xiaomipad5pro" target="_blank">
    <img src="../images/xiaomi01.webp" alt="">
    <h3 class="title">小米平板5 Pro</h3>
    <p class="desc">
      全新12代英特尔处理器，CNC一体精雕工艺，2.5K 120Hz高清屏，可选MX550独立显卡
    </p>
    <div class="price">
      <span class="new-price">2399元起</span>
      <span class="old-price">2499元</span>
    </div>
  </a>
</body>
</html>
```

```css
body, p, h3 {
  margin: 0;
  padding: 0;
}

body {
  background-color: #f5f5f5;
  font: 12px/1.5 Helvetica Neue,Helvetica,Arial,Microsoft Yahei,Hiragino Sans GB,Heiti SC,WenQuanYi Micro Hei,sans-serif;
}

h3 {
  font-weight: 400;
}

/* a的重置 */
a {
  text-decoration: none;
  color: #333;
  font-size: 12px;
}
```

![image-20230521224645953](../../../Coderwhy/pic/image-20230521224645953.png)

这里a已经修改为inline-block

![image-20230521225343984](../../../Coderwhy/pic/image-20230521225343984.png)

#### （3）水平居中的总结

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .box {
      background-color: #f00;
      text-align: center;
    }

    .box span {
      background-color: #0f0;
    }

    .container {
      background-color: #00f;
      width: 100px;
      height: 100px;
    }
  </style>
</head>
<body>
  
  <div class="box">
    <span>我是span元素</span>
    <div class="container"></div>
  </div>

</body>
</html>
```

![image-20230521230101455](../../../Coderwhy/pic/image-20230521230101455.png)